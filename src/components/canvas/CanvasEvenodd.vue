

<script setup>
import { ref, onMounted } from 'vue'
onMounted(() => {
    function draw() {
        var ctx = document.getElementById('canvas').getContext('2d')
        ctx.beginPath()
        ctx.arc(50, 50, 30, 0, Math.PI * 2, true)
        ctx.arc(50, 50, 15, 0, Math.PI * 2, true)
        //填充规则
        ctx.fill('')
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
