<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue'
import * as THREE from 'three'

const container = ref<HTMLDivElement | null>(null)

let renderer: THREE.WebGLRenderer | undefined

onMounted(() => {
  if (!container.value) return

  const scene = new THREE.Scene()
  scene.background = new THREE.Color(0x222222)

  const camera = new THREE.PerspectiveCamera(
    75,
    container.value.clientWidth / container.value.clientHeight,
    0.1,
    1000,
  )

  camera.position.z = 5

  renderer = new THREE.WebGLRenderer({ antialias: true })
  renderer.setSize(
    container.value.clientWidth,
    container.value.clientHeight,
  )

  container.value.appendChild(renderer.domElement)

  const geometry = new THREE.BoxGeometry()
  const material = new THREE.MeshBasicMaterial({ color: 0x00ffff })
  const cube = new THREE.Mesh(geometry, material)

  scene.add(cube)

  function animate() {
    if (!renderer) return

    cube.rotation.x += 0.01
    cube.rotation.y += 0.01

    renderer.render(scene, camera)
    requestAnimationFrame(animate)
  }

  animate()
})

onUnmounted(() => {
  renderer?.dispose()
})
</script>

<template>
  <div ref="container" class="scene"></div>
</template>

<style scoped>
.scene {
  width: 100%;
  height: 900px;
}
</style>
