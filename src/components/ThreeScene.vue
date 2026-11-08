<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue'
import * as THREE from 'three'
import { OrbitControls } from 'three/examples/jsm/Addons.js'


const container = ref<HTMLDivElement | null>(null)

let renderer: THREE.WebGLRenderer | undefined
let animationId = 0

onMounted(() => {
  if (!container.value) return

    // Setup renderer
  renderer = new THREE.WebGLRenderer({ antialias: true })
  renderer.setSize(
    container.value.clientWidth,
    container.value.clientHeight,
  )

  container.value.appendChild(renderer.domElement)

  const fov = 75;
  const aspect = container.value.clientWidth / container.value.clientHeight;
  const near = 0.1;
  const far = 10;
  const camera = new THREE.PerspectiveCamera(
    fov,
    aspect,
    near,
    far,
  )

  camera.position.z = 2

  const scene = new THREE.Scene()

  const controls = new OrbitControls(camera, renderer.domElement)
  controls.enableDamping = true
  controls.rotateSpeed = 0.4
  controls.dampingFactor = 0.10


  const geo = new THREE.IcosahedronGeometry(1.0, 3);
  const mat = new THREE.MeshStandardMaterial({
    color: 0xffffff,
    flatShading: true
  })

  const mesh = new THREE.Mesh(geo,mat);

  scene.add(mesh)

  const wiremat = new THREE.MeshBasicMaterial({
    color: 0xffffff,
    wireframe: true
  });

  const wireMesh = new THREE.Mesh(geo,wiremat);
  wireMesh.scale.setScalar(1.03)

  mesh.add(wireMesh)





  const hemiLight = new THREE.HemisphereLight(0x0099ff, 0xaa5500)

  scene.add(hemiLight)

  function animate(t = 0){
    requestAnimationFrame(animate)
    // mesh.rotation.y = t * 0.0001
    renderer?.render(scene, camera)
    controls.update();

  }

  animate()
})

onUnmounted(() => {
  cancelAnimationFrame(animationId)
  renderer?.dispose()
})
</script>

<template>
  <div>
    <p> Explore my skills and interests (WIP) </p>
  <div ref="container" class="scene"></div>
  </div>
</template>

<style scoped>
.scene {
  width: 100%;
  height: 100%;
}
</style>
