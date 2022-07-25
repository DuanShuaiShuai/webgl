

<script setup>
import { ref, onMounted } from 'vue'
onMounted(() => {
    function draw() {
        var ctx = document.getElementById('canvas').getContext('2d')
        var img = new Image()
        img.onload = function () {
            // ctx.drawImage(img, 10, 10, 50, 50)
            // ctx.beginPath()
            // ctx.moveTo(10, 10)
            // ctx.lineTo(70, 66)
            // ctx.lineTo(103, 76)
            // ctx.lineTo(170, 15)
            // ctx.stroke()
            // void ctx.drawImage(image, dx, dy, dWidth, dHeight)
            // void ctx.drawImage(image, sx, sy, sWidth, sHeight, dx, dy, dWidth, dHeight)
            ctx.drawImage(img, -10, -10, 100, 50, 0, 0, 200, 200)
        }
        img.src = 'https://staticcdn.pharmcube.com/images/logo.png'
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
