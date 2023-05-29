<template>
  <BasePlayer
    :previewImageLink="previewImageLink"
    :link="link"
    :isMuted="true"
    :isControls="false"
    @mouseover="turnOn"
    @mouseleave="turnOff"
  />
</template>

<script setup>
import BasePlayer from './BasePlayer.vue'

defineProps({
  previewImageLink: {
    type: String,
    default: ''
  },
  link: {
    type: String,
    default: ''
  },
})

function turnOn(e) {
  e.target.play()
}

function turnOff(e) {
  e.target.pause()
}
</script>
