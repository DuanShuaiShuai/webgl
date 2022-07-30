<template>
  <canvas id="canvas" height="300"></canvas>
</template>

<script setup>
import { onMounted } from 'vue'
onMounted(()=>{
   function draw() {
        var ctx = document.getElementById('canvas').getContext('2d');
        var sin = Math.sin(Math.PI/6);
        var cos = Math.cos(Math.PI/6);
        ctx.translate(150, 150);
        var c = 0;
        // ctx.fillStyle = "rgba(255, 128, 255, 0.5)";
        // ctx.fillRect(0, 50, 100, 100);
        // 水平方向的缩放 竖直方向的倾斜偏移 水平方向的倾斜偏移 竖直方向的缩放
        for (var i=0; i <= 12; i++) {
            c = Math.floor(255 / 12 * i);
            ctx.fillStyle = "rgb(" + c + "," + c + "," + c + ")";
            ctx.fillRect(0, 0, 150, 10);
            // 每次执行角度发生旋转，但是大小经过缩放与偏移保持不变
            ctx.transform(cos, sin, -sin, cos, 0, 0);
        }
        // ctx.setTransform(-1, 0, 0, 1, 100, 100);
        // ctx.fillStyle = "rgba(255, 128, 255, 0.5)";
        // ctx.fillRect(0, 50, 100, 100);
    }
    draw()
})

</script>
<style scoped>
#canvas{
  border: 1px solid #ccc;
}
</style>
