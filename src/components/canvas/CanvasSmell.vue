
<script setup>
import { ref, onMounted } from 'vue'
onMounted(() => {
    function draw() {
        var canvas = document.getElementById('paper')
        if (canvas.getContext) {
            var ctx = canvas.getContext('2d')

            ctx.beginPath()
            ctx.arc(75, 75, 50, 0, Math.PI * 2, true) // 绘制
            ctx.moveTo(110, 75)
            ctx.moveTo(75, 110)
            ctx.arc(75, 75, 35, 0, Math.PI, false) // 口 (顺时针)
            ctx.moveTo(65, 65)
            ctx.arc(60, 65, 5, 0, Math.PI * 2, true) // 左眼
            ctx.moveTo(95, 65)
            ctx.arc(90, 65, 5, 0, Math.PI * 2, true) // 右眼
            ctx.stroke()
            // 一个非常有用的函数，而这个函数实际上并不能画出任何东西，也是上面所描述的路径列表的一部分，这个函数就是moveTo()。或者你可以想象一下在纸上作业，一支钢笔或者铅笔的笔尖从一个点到另一个点的移动过程。
            // 如果你想看到连续的线，你可以移除调用的 moveTo()。
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
