<script setup>
import { ref, onMounted } from 'vue'
import { loadImage, getImageData, traverse } from './utils.js'
onMounted(() => {
    const canvas = document.getElementById('paper')
    const context = canvas.getContext('2d')
    ;(async function () {
        // 异步加载图片
        const img = await loadImage('https://p2.ssl.qhimg.com/d/inn/4b7e384c55dc/girl1.jpg')
        // 获取图片的 imageData 数据对象
        const imageData = getImageData(img)
        console.log({ imageData })
        // 遍历 imageData 数据对象
        traverse(imageData, ({ r, g, b, a }) => {
            // 对每个像素进行灰度化处理
            const v = 0.2126 * r + 0.7152 * g + 0.0722 * b
            return [v, v, v, a]
        })
        // 更新canvas内容
        canvas.width = imageData.width
        canvas.height = imageData.height
        context.putImageData(imageData, 0, 0)
    })()
})
</script>

<template>
    <div>
        <canvas id="paper" width="0" height="0"></canvas>
    </div>
</template>
<style scoped>
canvas {
    background-image: linear-gradient(to right, transparent 90%, #000 0);
    background-size: 8px 8px, 8px 8px;
}
</style>
