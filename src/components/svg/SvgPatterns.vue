<template>
<svg width="200" height="200" xmlns="http://www.w3.org/2000/svg" version="1.1">
  <defs>
    <linearGradient id="Gradient1">
      <stop offset="5%" stop-color="white"/>
      <stop offset="95%" stop-color="blue"/>
    </linearGradient>
    <linearGradient id="Gradient2" x1="0" x2="0" y1="0" y2="1">
      <stop offset="5%" stop-color="red"/>
      <stop offset="95%" stop-color="orange"/>
    </linearGradient>

    <pattern patternContentUnits="objectBoundingBox" id="Pattern" width=".25" height=".25">
       <rect x="0" y="0" width=".25" height=".25" fill="skyblue"/>
    <rect x="0" y="0" width=".125" height=".125" fill="url(#Gradient2)"/>
    <circle cx=".125" cy=".125" r=".1" fill="url(#Gradient1)" fill-opacity="0.5"/> 
    </pattern>
     <!-- <pattern id="Pattern" width=".25" height=".25" patternContentUnits="objectBoundingBox">
   <rect x="0" y="0" width=".25" height=".25" fill="skyblue"/>
   <rect x="0" y="0" width=".125" height=".125" fill="url(#Gradient2)"/>
   <circle cx=".125" cy=".125" r=".1" fill="url(#Gradient1)" fill-opacity="0.5"/> -->
 <!-- </pattern> -->

  </defs>

  <rect fill="url(#Pattern)" stroke="black" x="0" y="0" width="200" height="200"/>
</svg>
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
