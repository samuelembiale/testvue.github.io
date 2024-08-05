<script setup>  
  import { ref } from 'vue'

  const sceneRef = ref(null)
  defineExpose({ sceneRef })
</script>

<template>
   <a-scene 
   ref="sceneRef"
   mindar-image="imageTargetSrc: ./assets/targets.mind; filterMinCF:0.0001; filterBeta: 0.001; autoStart: false; uiLoading: no; uiError: no; uiScanning: no;" color-space="sRGB"  embedded
        renderer="colorManagement: true, physicallyCorrectLights" vr-mode-ui="enabled: false"
        device-orientation-permission-ui="enabled: false">
        <a-assets>
            <!-- <img id="card" src="example2/pattern-Ar-Marker-katherine.png" /> -->
            <a-asset-item id="avatarModel" src="./assets/saturn_nasa.glb"></a-asset-item>
        </a-assets>
        <a-camera position="0 0 0" look-controls="enabled: false"></a-camera>
        <a-entity mindar-image-target="targetIndex: 0">
            <!-- <a-plane src="#card" position="0 0 0" height="1" width="1" rotation="0 0 0"></a-plane> -->
            <a-gltf-model rotation="90 0 0" position="0 0 0" scale="0.04 0.02 0.04" src="#avatarModel" animation-mixer>
            </a-gltf-model>
        </a-entity>
    </a-scene>
</template>