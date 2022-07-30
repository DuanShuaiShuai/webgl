<template>
  <canvas id="canvas"></canvas>
</template>

<script setup>
import { onMounted } from 'vue'
onMounted(()=>{
    function draw() {
    var ctx = document.getElementById('canvas').getContext('2d');

    // draw a simple rectangle, but scale it.
    ctx.save();
   
    ctx.translate(0,75); 
    ctx.scale(1,-1) //以 y 轴作为对称轴镜像反转，就可得到著名的笛卡尔坐标系，左下角为原点
    ctx.moveTo(0,0)
    ctx.lineTo(300,0)
    ctx.stroke()
    ctx.fillRect(10, 10, 10, 10);

    ctx.restore();

    // mirror horizontally
    // ctx.scale(-1, 1);
    // ctx.font = '48px serif';
    // ctx.fillText('MDN', 10, 120);
    }
    draw()
})

</script>
<style scoped>
#canvas{
  border: 1px solid #ccc;
}
</style>
