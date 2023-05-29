<template>
  <BasePlayer
    :previewImageLink="previewImageLink"
    :link="link"
    :progress="progress"
    :isMuted="isMuted"
    :isControls="isControls"
    @pause="pause"
  />
</template>

<script setup>
import BasePlayer from './BasePlayer.vue'

const emit = defineEmits(['pause'])

defineProps({
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
  isMuted: {
    type: Boolean,
    default: false
  },
  isControls: {
    type: Boolean,
    default: true
  },
})

function pause(currentTime) {
  emit('pause', currentTime)
}
</script>
