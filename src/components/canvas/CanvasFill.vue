<template>
  <canvas id="canvas" width="600" height="600"></canvas>
</template>

<script setup>
import {Vector2D} from '../utils/vector2d';
import { onMounted } from 'vue'
onMounted(()=>{      
    var ctx = document.getElementById('canvas').getContext('2d');
    ctx.translate(300,300); ctx.scale(1, -1);
    const points = [new Vector2D(0, 100)];
    for(let i = 1; i <= 4; i++) {
    const p = points[0].copy().rotate(i * Math.PI * 0.4);
    points.push(p);
    }

    const polygon = [
    ...points,
    ];

    // 绘制正五边形
    ctx.save();
    ctx.translate(-128, 0);
    draw(ctx, polygon);
    ctx.restore();

    const stars = [
    points[0],
    points[2],
    points[4],
    points[1],
    points[3],
    ];

    // 绘制正五角星
    ctx.save();
    ctx.translate(128, 0);
    draw(ctx, stars);
    ctx.restore();
    function draw(context, points, {
    fillStyle = 'black',
    close = false,
    rule = 'nonzero',
    } = {}) {
    context.beginPath();
    context.moveTo(...points[0]);
    for(let i = 1; i < points.length; i++) {
        context.lineTo(...points[i]);
    }
    if(close) context.closePath();
    context.fillStyle = fillStyle;
    context.fill(rule);
    }

})

</script>
<style scoped>
#canvas{
  border: 1px solid #ccc;
}
</style>
