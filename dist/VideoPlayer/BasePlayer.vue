<template>
  <video
    @pause="pause"
    @ended="pause"
    @keyup="changeSpeed"
    ref="video"
    :poster="previewImageLink"
    :controls="isControls"
    :title="title"
  >
    <source
      :src="link"
      type="application/x-mpegURL"
    />
  </video>
</template>

<script setup>
import { onMounted, onUpdated, ref } from 'vue'
import Hls from 'hls.js'

const props = defineProps({
  previewImageLink: {
    type: String,
    default: ''
  },
  link: {
    type: String,
    default: ''
  },
  progress: {
    type: Number,
    default: 0
  },
  title: {
    type: String,
    default: ''
  },
  isMuted: {
    type: Boolean,
    default: false
  },
  isControls: {
    type: Boolean,
    default: true
  },
})

const emit = defineEmits(['pause', 'test'])
const video = ref(null)

onMounted(() => {
  prepareVideoPlayer()
})

onUpdated(() => {
  prepareVideoPlayer()
})

function prepareVideoPlayer() {
  let hls = new Hls()
  let stream = props.link
  hls.loadSource(stream)
  if (video.value) {
    hls.attachMedia(video.value)
    video.value.muted = props.isMuted
    video.value.currentTime = props.progress
  }
}

function pause() {
  const currentTime = video?.value?.currentTime || 0

  emit('pause', currentTime)
}

function changeSpeed(e) {
  if (e.key === 'w' && video.value) {
    video.value.playbackRate = video.value.playbackRate + 0.25
  } else if (e.key === 's' && video.value) {
    video.value.playbackRate = video.value.playbackRate - 0.25
  }
}
</script>
