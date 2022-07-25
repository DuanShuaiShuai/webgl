
<script setup>
import { ref, onMounted } from 'vue'
onMounted(() => {
    function draw() {
        var canvas = document.getElementById('paper')
        // if (canvas.getContext) {
        var ctx = canvas.getContext('2d')
        // for (var i = 0; i < 4; i++) {
        //     for (var j = 0; j < 3; j++) {
        //         ctx.beginPath()
        //         var x = 25 + j * 50 // x 坐标值
        //         var y = 25 + i * 50 // y 坐标值
        //         var radius = 20 // 圆弧半径
        //         var startAngle = 0 // 开始点
        //         var endAngle = Math.PI + (Math.PI * j) / 2 // 结束点
        //         var anticlockwise = i % 2 == 0 ? false : true // 顺时针或逆时针

        //         ctx.arc(x, y, radius, startAngle, endAngle, anticlockwise)

        //         if (i > 1) {
        //             ctx.fill()
        //         } else {
        //             ctx.stroke()
        //         }
        //     }
        // }
        // }

        ctx.setLineDash([7, 7])
        ctx.beginPath()
        ctx.moveTo(150, 20)
        ctx.arcTo(150, 100, 50, 20, 60)
        ctx.stroke()

        ctx.fillStyle = 'blue'
        // base point
        ctx.fillRect(150, 20, 10, 10)

        ctx.fillStyle = 'red'
        // control point one
        ctx.fillRect(150, 100, 10, 10)
        // control point two
        ctx.fillRect(50, 20, 10, 10)
        //
        ctx.setLineDash([5, 5])
        ctx.moveTo(150, 20)
        ctx.lineTo(150, 100)
        ctx.lineTo(50, 20)
        ctx.stroke()
        ctx.beginPath()
        ctx.arc(120, 38, 30, 0, 2 * Math.PI)
        ctx.stroke()
    }
    draw()
})
</script>

<template>
    <canvas id="paper" width="500" height="500"></canvas>
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
