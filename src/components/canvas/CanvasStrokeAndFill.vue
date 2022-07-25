
<script setup>
import { ref, onMounted } from 'vue'
onMounted(() => {
    function draw() {
        var canvas = document.getElementById('paper')
        if (canvas.getContext) {
            var ctx = canvas.getContext('2d')

            // 填充三角形
            ctx.beginPath()
            ctx.moveTo(25, 25)
            ctx.lineTo(105, 25)
            ctx.lineTo(25, 105)
            ctx.fill() // 使用fill会默认闭合路径

            // 描边三角形
            ctx.beginPath()
            ctx.moveTo(125, 125)
            ctx.lineTo(125, 45)
            ctx.lineTo(45, 125)
            ctx.closePath()
            ctx.stroke() //stroke的话需要手动调用closePath关闭路径
        }
    }
    draw()
})
</script>

<template>
    <canvas id="paper" width="200" height="200"></canvas>
</template>
<style scoped>
canvas {
    width: 200px;
    height: 200px;
    border: 1px solid #ccc;
    /* background-image: linear-gradient(to right, transparent 90%, #000 0);
    background-size: 20px 20px, 20px 20px; */
}
</style>
