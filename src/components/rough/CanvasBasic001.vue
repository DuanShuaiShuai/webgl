

<script setup>
import { ref, onMounted } from 'vue'
import rough from 'roughjs'
onMounted(() => {
    const rc = rough.canvas(document.querySelector('canvas'))
    const ctx = rc.ctx
    ctx.translate(256, 256)
    ctx.scale(1, -1)
    const hillOpts = { roughness: 1.5, strokeWidth: 2, fill: 'blue' }
    rc.path('M-160 0L-80 100L20 0', hillOpts)
    rc.path('M160 0L80 100L-20 0', hillOpts)
    rc.circle(0, 256 - 106, 105, { stroke: 'red', strokeWidth: 4, fill: 'rgba(255, 255, 0, 0.4)', fillStyle: 'solid' })
})
</script>

<template>
    <canvas id="canvas" width="512" height="256"></canvas>
</template>
<style scoped>
canvas {
    width: 900px;
    height: 450px;
    border: 1px solid #ccc;
}
</style>
