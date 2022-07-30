<template>
 <div>
    <svg version="1.1"
        viewBox="0 0 600 200"
        width="300" height="200"
        xmlns="http://www.w3.org/2000/svg">
        <rect width="100%" height="100%" fill="red" />
        <circle cx="150" cy="100" r="80" fill="green" />
        <text x="150" y="125" font-size="60" text-anchor="middle" fill="white">SVG</text>
    </svg>
 </div>
</template>

<script setup>
import { onMounted } from 'vue'
onMounted(()=>{
})

</script>
<style scoped>
#canvas{
  border: 1px solid #ccc;
}
</style>
