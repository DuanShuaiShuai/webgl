<template>
 <div>
    <svg width="200" height="250" version="1.1" xmlns="http://www.w3.org/2000/svg">
        <!-- <rect x="10" y="10" width="30" height="30"/>
        <rect x="60" y="10" rx="15" ry="15" width="30" height="30"/>
        <circle cx="25" cy="75" r="20"/>
        <ellipse cx="75" cy="75" rx="20" ry="5"/> -->
        <!-- <polyline points="0 0, 40 10, 40 110,100 300"/>

        <polygon points="100 100, 140 110, 120 140"/> -->
        <path d="M 20 20 Q 140 205, 50 230 T 90230"/>
        <!-- <line x1="10" x2="50" y1="110" y2="150"/> -->
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
