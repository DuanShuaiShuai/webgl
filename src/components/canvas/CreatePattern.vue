

<script setup>
import { ref, onMounted } from 'vue'
onMounted(() => {
    function draw() {
        var ctx = document.getElementById('canvas').getContext('2d')

        // 创建新 image 对象，用作图案
        var img = new Image()
        img.src = 'https://staticcdn.pharmcube.com/images/logo.png'
        img.onload = function () {
            // 创建图案
            var ptrn = ctx.createPattern(img, 'repeat')
            ctx.fillStyle = ptrn
            ctx.fillRect(0, 0, 150, 150)
        }
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
