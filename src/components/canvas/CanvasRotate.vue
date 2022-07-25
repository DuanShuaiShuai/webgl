

<script setup>
import { ref, onMounted } from 'vue'
onMounted(() => {
    function draw() {
        var ctx = document.getElementById('canvas').getContext('2d')
        ctx.translate(100, 100)

        for (var i = 1; i < 8; i++) {
            // Loop through rings (from inside to out)
            ctx.save()
            ctx.fillStyle = 'rgb(' + 51 * i + ',' + (255 - 51 * i) + ',255)'

            for (var j = 0; j < i * 6; j++) {
                // draw individual dots
                ctx.rotate((Math.PI * 2) / (i * 6))
                ctx.beginPath()
                ctx.arc(0, i * 12.5, 5, 0, Math.PI * 2, true)
                ctx.fill()
            }

            ctx.restore()
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