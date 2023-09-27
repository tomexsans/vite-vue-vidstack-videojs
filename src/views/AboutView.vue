<script setup>
import 'video.js/dist/video-js.css'
import { ref,onMounted } from 'vue';
import videojs from 'video.js';
import 'videojs-contrib-quality-levels';
import qalitySelectorHls from 'videojs-quality-selector-hls' // npm linked

const videoPlayer = ref(null)

onMounted(()=>{
  videojs.registerPlugin('qalitySelectorHls',qalitySelectorHls);
  const player = videojs(videoPlayer.value)
  player.qalitySelectorHls()
})

</script>

<template>
  <div class="about">
    <video ref="videoPlayer" id="videojs-quality-selector-hls-player" class="video-js vjs-default-skin" controls>
    <source src="https://test-streams.mux.dev/x36xhzz/x36xhzz.m3u8" type="application/x-mpegURL">
  </video>
  </div>
</template>

<style>
#videojs-quality-selector-hls-player{
  width: 100%;
  height: 50vh;
}
</style>
