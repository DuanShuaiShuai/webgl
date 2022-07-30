<template>
 <div>
    <svg width="120" height="120" version="1.1"
  xmlns="http://www.w3.org/2000/svg">
  <defs>
      <radialGradient id="Gradient" cx="0.5" cy="0.5" r="0.5" fr="0.2"  fx="0.5" fy="0.5">
        <stop offset="0%" stop-color="red"/>
        <stop offset="100%" stop-color="blue"/>
      </radialGradient>
  </defs>

  <rect x="10" y="10" rx="15" ry="15" width="100" height="100"
        fill="url(#Gradient)" stroke="black" stroke-width="2"/>

  <circle cx="60" cy="60" r="50" fill="transparent" stroke="white" stroke-width="2"/>
  <circle cx="35" cy="35" r="2" fill="white" stroke="white"/>
  <circle cx="60" cy="60" r="2" fill="white" stroke="white"/>
  <text x="38" y="40" fill="white" font-family="sans-serif" font-size="10pt">(fx,fy)</text>
  <text x="63" y="63" fill="white" font-family="sans-serif" font-size="10pt">(cx,cy)</text>

</svg>
    <svg width="200" height="250" version="1.1" xmlns="http://www.w3.org/2000/svg">
         <rect x="10" y="10" width="100" height="100" stroke="blue" fill="purple"
       fill-opacity="0.5" stroke-opacity="0.8"/>
        <!-- <rect x="10" y="10" width="30" height="30"/>
        <rect x="60" y="10" rx="15" ry="15" width="30" height="30"/>
        <circle cx="25" cy="75" r="20"/>
        <ellipse cx="75" cy="75" rx="20" ry="5"/> -->
        <!-- <polyline points="0 0, 40 10, 40 110,100 300"/>

        <polygon points="100 100, 140 110, 120 140"/> -->
        <path d="M 20 20 Q 140 205, 50 230 T 90230"/>
        <!-- <line x1="10" x2="50" y1="110" y2="150"/> -->
    </svg>
    <svg width="190px" height="160px" version="1.1" xmlns="http://www.w3.org/2000/svg">

    <path d="M10 10 C 20 20, 40 20, 50 10" stroke="black" fill="transparent"/>
    <path d="M70 10 C 70 20, 120 20, 120 10" stroke="black" fill="transparent"/>
    <path d="M130 10 C 120 20, 180 20, 170 10" stroke="black" fill="transparent"/>
    <path d="M10 60 C 20 80, 40 80, 50 60" stroke="black" fill="transparent"/>
    <path d="M70 60 C 70 80, 110 80, 110 60" stroke="black" fill="transparent"/>
    <path d="M130 60 C 120 80, 180 80, 170 60" stroke="black" fill="transparent"/>
    <path d="M10 110 C 20 140, 40 140, 50 110" stroke="black" fill="transparent"/>
    <path d="M70 110 C 70 140, 110 140, 110 110" stroke="black" fill="transparent"/>
    <path d="M130 110 C 120 140, 180 140, 170 110" stroke="black" fill="transparent"/>

    </svg>

    <svg width="190px" height="160px" version="1.1" xmlns="http://www.w3.org/2000/svg">
  <path d="M10 80 C 40 10, 65 10, 95 80 S 150 150, 180 80" stroke="black" fill="transparent"/>
</svg>
<svg width="160" height="140" xmlns="http://www.w3.org/2000/svg" version="1.1">
  <line x1="40" x2="120" y1="20" y2="20" stroke="black" stroke-width="20" stroke-linecap="butt"/>
  <line x1="40" x2="120" y1="60" y2="60" stroke="black" stroke-width="20" stroke-linecap="square"/>
  <line x1="40" x2="120" y1="100" y2="100" stroke="black" stroke-width="20" stroke-linecap="round"/>
</svg>
<svg width="160" height="280" xmlns="http://www.w3.org/2000/svg" version="1.1">
  <polyline points="40 60 80 20 120 60" stroke="black" stroke-width="20"
      stroke-linecap="butt" fill="none" stroke-linejoin="miter"/>

  <polyline points="40 140 80 100 120 140" stroke="black" stroke-width="20"
      stroke-linecap="round" fill="none" stroke-linejoin="round"/>

  <polyline points="40 220 80 180 120 220" stroke="black" stroke-width="20"
      stroke-linecap="square" fill="none" stroke-linejoin="bevel"/>
</svg>
<svg width="200" height="150" xmlns="http://www.w3.org/2000/svg" version="1.1">
  <path d="M 10 75 Q 50 10 100 75 T 190 75" stroke="black"
    stroke-linecap="round" stroke-dasharray="5,10,5" fill="none"/>
  <path d="M 10 75 L 190 75" stroke="red"
    stroke-linecap="round" stroke-width="1" stroke-dasharray="5,5" fill="none"/>
</svg>
<svg width="120" height="240" version="1.1" xmlns="http://www.w3.org/2000/svg">
    <defs>
        <radialGradient id="RadialGradient1">
            <stop offset="0%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient>
        <radialGradient id="RadialGradient2" cx="0.5" cy="0.5" r="1">
            <stop offset="0%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient>
    </defs>
    <rect x="10" y="10" rx="15" ry="15" width="100" height="100" fill="url(#RadialGradient1)"/>
    <rect x="10" y="120" rx="15" ry="15" width="100" height="100" fill="url(#RadialGradient2)"/>
</svg>

<svg width="220" height="220" version="1.1" xmlns="http://www.w3.org/2000/svg">
    <defs>
        <radialGradient id="GradientPad" gradientUnits="objectBoundingBox"
             cx="60" cy="60" r="50" fx="35" fy="35"
                spreadMethod="pad"
            >
            <stop offset="0%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient>
         <radialGradient id="Gradient" cx="60" cy="60" r="50" fx="35" fy="35" gradientUnits="userSpaceOnUse"></radialGradient>
        <!-- <radialGradient id="GradientRepeat"
                cx="0.5" cy="0.5" r="0.4" fx="0.75" fy="0.75"
                spreadMethod="repeat">
            <stop offset="0%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient>
        <radialGradient id="GradientReflect"
                cx="0.5" cy="0.5" r="0.4" fx="0.75" fy="0.75"
                spreadMethod="reflect">
            <stop offset="0%" stop-color="red"/>
            <stop offset="100%" stop-color="blue"/>
        </radialGradient> -->
    </defs>
    <rect x="10" y="10" rx="15" ry="15" width="100" height="100" fill="url(#GradientPad)"/>
    <rect x="10" y="120" rx="15" ry="15" width="100" height="100" fill="url(#Gradient)"/>
    <!-- <rect x="10" y="120" rx="15" ry="15" width="100" height="100" fill="url(#GradientRepeat)"/>
    <rect x="120" y="120" rx="15" ry="15" width="100" height="100" fill="url(#GradientReflect)"/>
    <text x="15" y="30" fill="white" font-family="sans-serif" font-size="12pt">Pad</text>
    <text x="15" y="140" fill="white" font-family="sans-serif" font-size="12pt">Repeat</text>
    <text x="125" y="140" fill="white" font-family="sans-serif" font-size="12pt">Reflect</text> -->
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
