

<script setup>
import { ref, onMounted } from 'vue'
onMounted(() => {
    function draw() {
        var canvas = document.getElementById('canvas')
        var ctx = canvas.getContext('2d')

        ctx.rect(10, 10, 100, 100)
        ctx.stroke()
        console.log(ctx.isPointInPath(9, 10)) // false
        console.log(ctx.isPointInPath(10, 10)) // true
        console.log(ctx.isPointInPath(11, 10)) // true
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
