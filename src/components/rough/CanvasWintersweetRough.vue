

<script setup>
import { ref, onMounted } from 'vue'
import rough from 'roughjs'
import { Vector2D } from '../../utils/vector2d.js'
// import rough from 'roughjs'
onMounted(() => {
    // const canvas = document.querySelector('canvas')
    // const ctx = canvas.getContext('2d')
    const rc = rough.canvas(document.querySelector('canvas'))
    const ctx = rc.ctx

    ctx.translate(0, canvas.height)
    ctx.scale(1, -1)
    ctx.lineCap = 'round'

    /**
     * @param {*} context canvas上下文
     * @param {*} v0 向量
     * @param {*} length 树干长度
     * @param {*} thickness 树干粗细
     * @param {*} dir 旋转角度
     * @param {*} bias
     */

    function drawBranch(context, v0, length, thickness, dir, bias) {
        const v = new Vector2D().rotate(dir).scale(length)
        const v1 = v0.copy().add(v)
        const hillOpts = { roughness: 3.5, strokeWidth: thickness, fill: 'black' }
        rc.path(`M${v0.x} ${v0.y}L${v1.x} ${v1.y}`, hillOpts)
        // context.lineWidth = thickness
        // context.beginPath()
        // context.moveTo(...v0)
        // context.lineTo(...v1)
        // context.stroke()
        if (thickness > 2) {
            const left = Math.PI / 4 + 0.5 * (dir + 0.2) + bias * (Math.random() - 0.5)
            drawBranch(context, v1, length * 0.9, thickness * 0.8, left, bias * 0.9)
            const right = Math.PI / 4 + 0.5 * (dir - 0.2) + bias * (Math.random() - 0.5)
            drawBranch(context, v1, length * 0.9, thickness * 0.8, right, bias * 0.9)
        }

        if (thickness < 5 && Math.random() < 0.3) {
            context.save()
            context.strokeStyle = '#c72c35'
            const th = Math.random() * 6 + 3
            context.lineWidth = th
            context.beginPath()
            context.moveTo(...v1)
            context.lineTo(v1.x, v1.y - 2)
            context.stroke()
            context.restore()
        }
    }

    const v0 = new Vector2D(256, 0)
    drawBranch(ctx, v0, 50, 10, 1.5, 3)
})
</script>

<template>
    <canvas id="canvas" width="512" height="400"></canvas>
</template>
<style scoped>
canvas {
    border: 1px solid #ccc;
}
</style>
