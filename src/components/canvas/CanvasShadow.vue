

<script setup>
import { ref, onMounted } from 'vue'
onMounted(() => {
    function draw() {
        var ctx = document.getElementById('canvas').getContext('2d')
        var lingrad = ctx.createLinearGradient(0, 0, 0, 150)
        lingrad.addColorStop(0, '#00ABEB')
        lingrad.addColorStop(0.1, 'red')
        lingrad.addColorStop(0.5, '#0000ff')
        lingrad.addColorStop(1, '#fff')
        ctx.shadowOffsetX = 2
        ctx.shadowOffsetY = 2
        ctx.shadowBlur = 5
        ctx.shadowColor = 'rgba(0, 0, 0, 0.5)'

        ctx.font = '20px Times New Roman'
        ctx.fillStyle = lingrad
        ctx.fillText('Sample String', 5, 30)
    }
    draw()
})
</script>

<template>
    <canvas id="canvas" width="200" height="200"></canvas>
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
