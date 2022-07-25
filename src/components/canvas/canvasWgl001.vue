

<script setup>
import { ref, onMounted } from 'vue'
import * as d3 from 'd3'
onMounted(() => {
    const canvas = document.querySelector('canvas')
    const gl = canvas.getContext('webgl')
    // 顶点着色器（Vertex Shader）
    // 顶点着色器理解为处理顶点的 GPU 程序代码。它可以改变顶点的信息（如顶点的坐标、法线方向、材质等等），从而改变我们绘制出来的图形的形状或者大小等等。
    // WebGL 从顶点着色器和图元提取像素点给片元着色器执行代码的过程，就是我们前面说的生成光栅信息的过程，我们也叫它光栅化过程。所以，片元着色器的作用，就是处理光栅化后的像素信息。
    const vertex = `
      attribute vec2 position;
      varying vec3 color;
      void main() {
        gl_PointSize = 1.0;
        color = vec3(0.5 + position * 0.5, 0.0);
        gl_Position = vec4(position * 0.5, 1.0, 1.0);
      }
    `
    // 片段着色器（Fragment Shader）
    const fragment = `
      precision mediump float;
      varying vec3 color;
      void main()
      {
        gl_FragColor = vec4(color, 1.0);
      }    
    `

    // 用顶点着色器和片元着色器代码，来创建 WebGL 程序
    // 用于创建一个 WebGLShader 着色器对象，该对象可以使用 WebGLRenderingContext.shaderSource() 和 WebGLRenderingContext.compileShader() 方法配置着色器代码。
    const vertexShader = gl.createShader(gl.VERTEX_SHADER)
    gl.shaderSource(vertexShader, vertex) //设置 WebGLShader 着色器（顶点着色器及片元着色器）的 GLSL 程序代码。
    gl.compileShader(vertexShader) //WebGL API下的方法 WebGLRenderingContext.compileShader() 用于编译一个 GLSL 着色器，使其成为为二进制数据，然后就可以被WebGLProgram对象所使用。
    // 创建一个片段
    const fragmentShader = gl.createShader(gl.FRAGMENT_SHADER)
    gl.shaderSource(fragmentShader, fragment)
    gl.compileShader(fragmentShader)

    // 创建 WebGLProgram 对象，并。，然后
    const program = gl.createProgram() //WebGL API 的 WebGLRenderingContext.createProgram() 方法用于创建和初始化一个 WebGLProgram 对象。
    //将这两个 shader 关联到这个 WebGL 程序上 WebGLProgram 对象的创建过程主要是添加 vertexShader 和 fragmentShader
    gl.attachShader(program, vertexShader) //添加预先定义好的顶点着色器和片段着色器
    gl.attachShader(program, fragmentShader) //添加预先定义好的顶点着色器和片段着色器
    // 将这个 WebGLProgram 对象链接到 WebGL 上下文对象上
    gl.linkProgram(program) //WebGLRenderingContext 接口的linkProgram()方法链接给定的WebGLProgram，从而完成为程序的片元和顶点着色器准备 GPU 代码的过程。
    // 通过 useProgram 选择启用这个 WebGLProgram 对象
    gl.useProgram(program) //方法将定义好的WebGLProgram 对象添加到当前的渲染状态中。

    const points = new Float32Array([-1, -1, 0, 1, 1, -1])
    // 我们要将定义好的数据写入 WebGL 的缓冲区
    // 这个过程我们可以简单总结为三步，分别是创建一个缓存对象，将它绑定为当前操作对象，再把当前的数据写入缓存对象。这三个步骤主要是利用 createBuffer、bindBuffer、bufferData 方法来实现的，过程很简单你可以看一下我下面给出的实现代码。
    const bufferId = gl.createBuffer()
    gl.bindBuffer(gl.ARRAY_BUFFER, bufferId)
    gl.bufferData(gl.ARRAY_BUFFER, points, gl.STATIC_DRAW)

    //在 GLSL 中，attribute 表示声明变量，vec2 是变量的类型，它表示一个二维向量，position 是变量名。接下来我们将 buffer 的数据绑定给顶点着色器的 position 变量
    const vPosition = gl.getAttribLocation(program, 'position') //获取顶点着色器中的position变量的地址
    gl.vertexAttribPointer(vPosition, 2, gl.FLOAT, false, 0, 0) // 告诉显卡从当前绑定的缓冲区（bindBuffer() 指定的缓冲区）中读取顶点数据。 给变量设置长度和类型
    gl.enableVertexAttribArray(vPosition) //激活这个变量

    // 我们先调用 gl.clear 将当前画布的内容清除，然后调用 gl.drawArrays 传入绘制模式。这里我们选择 gl.TRIANGLES 表示以三角形为图元绘制，再传入绘制的顶点偏移量和顶点数量，WebGL 就会将对应的 buffer 数组传给顶点着色器，并且开始绘制。
    gl.clear(gl.COLOR_BUFFER_BIT) //使用预设值来清空缓冲。
    // 从第一个点 开始绘画三个点
    gl.drawArrays(gl.TRIANGLES, 0, points.length / 2)
})
</script>

<template>
    <canvas id="canvas" width="300" height="300"></canvas>
</template>
<style scoped>
canvas {
    width: 150px;
    height: 150px;
    border: 1px solid #ccc;
}
</style>
