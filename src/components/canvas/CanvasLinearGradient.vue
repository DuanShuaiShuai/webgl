

<script setup>
import { ref, onMounted } from 'vue'
onMounted(() => {
    function draw() {
        var ctx = document.getElementById('paper').getContext('2d')

        // Create gradients
        var lingrad = ctx.createLinearGradient(0, 0, 0, 150)
        lingrad.addColorStop(0, '#00ABEB')
        lingrad.addColorStop(0.5, '#fff')
        lingrad.addColorStop(0.5, '#0000ff')
        lingrad.addColorStop(1, '#fff')

        var lingrad2 = ctx.createLinearGradient(0, 50, 0, 95)
        lingrad2.addColorStop(0.5, '#000')
        lingrad2.addColorStop(1, 'rgba(0,0,0,0)')

        // assign gradients to fill and stroke styles
        ctx.fillStyle = lingrad
        ctx.strokeStyle = lingrad2

        // draw shapes
        ctx.fillRect(10, 10, 130, 130)
        ctx.strokeRect(50, 50, 50, 50)
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
