

<script setup>
import { ref, onMounted } from 'vue'
import * as d3 from 'd3'
onMounted(() => {
    const dataSource = 'https://s5.ssl.qhres2.com/static/b0695e2dd30daa64.json'
    console.log({ d3 })
    /* globals d3 */
    ;(async function () {
        const data = await (await fetch(dataSource)).json()
        const regions = d3
            .hierarchy(data)
            .sum((d) => 1)
            .sort((a, b) => b.value - a.value)

        const pack = d3.pack().size([2000, 2000]).padding(3)

        const root = pack(regions) // 处理成的数据结构
        console.log({ root })
        const canvas = document.querySelector('canvas')
        const context = canvas.getContext('2d')
        const TAU = 2 * Math.PI

        function draw(ctx, node, { fillStyle = 'rgba(0, 0, 0, 0.2)', textColor = 'white' } = {}) {
            const children = node.children
            const { x, y, r } = node
            ctx.fillStyle = fillStyle
            ctx.beginPath()
            ctx.arc(x, y, r, 0, TAU)
            ctx.fill()
            if (children) {
                for (let i = 0; i < children.length; i++) {
                    draw(context, children[i])
                }
            } else {
                const name = node.data.name
                ctx.fillStyle = textColor
                ctx.font = '1.5rem Arial'
                ctx.textAlign = 'center'
                ctx.fillText(name, x, y)
            }
        }
        draw(context, root)
    })()
})
</script>

<template>
    <canvas id="canvas" width="2000" height="2000"></canvas>
</template>
<style scoped>
canvas {
    width: 900px;
    height: 900px;
    border: 1px solid #ccc;
}
</style>
