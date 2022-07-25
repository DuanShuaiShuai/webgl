
<script setup>
// Canvas 元素上的 width 和 height 属性不等同于 Canvas 元素的 CSS 样式的属性。
// 这是因为，CSS 属性中的宽高影响 Canvas 在页面上呈现的大小，而 HTML 属性中的宽高
// 则决定了 Canvas 的坐标系。为了区分它们，我们称 Canvas 的 HTML 属性宽高为画布宽高，
// CSS 样式宽高为样式宽高。
// 注意：
// 行内的宽高决定的是坐标系的大小
// 样式宽高决定的是页面上呈现的大小
import { ref, onMounted } from 'vue'
onMounted(() => {
    const canvas = document.getElementById('paper')
    const ctx = canvas.getContext('2d')
    ctx.fillStyle = 'green'
    //绘制矩形
    ctx.fillRect(0, 0, 200, 100)
})
</script>

<template>
    <canvas id="paper" width="400" height="400"></canvas>
</template>
<style scoped>
canvas {
    width: 200px;
    height: 200px;
    background-image: linear-gradient(to right, transparent 90%, #000 0);
    background-size: 20px 20px, 20px 20px;
}
</style>
