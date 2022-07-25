

<script setup>
import { ref, onMounted } from 'vue'
onMounted(() => {
    function draw() {
        var ctx = document.getElementById('canvas').getContext('2d')
        ctx.font = '48px serif'
        ctx.fillText('Hello world', 10, 50)
        ctx.strokeText('Hello world2', 10, 150)

        //获取文本的宽度
        //https://developer.mozilla.org/zh-CN/docs/Web/API/TextMetricsx
        console.log(ctx.measureText('Hello world'))
        console.log(ctx.measureText('Hello world2'))
    }
    draw()
})
</script>

<template>
    <canvas id="canvas" width="400" height="200"></canvas>
</template>
<style scoped>
canvas {
    width: 400px;
    height: 200px;
    border: 1px solid #ccc;
    /* background-image: linear-gradient(to right, transparent 90%, #000 0);
    background-size: 20px 20px, 20px 20px; */
}
</style>
