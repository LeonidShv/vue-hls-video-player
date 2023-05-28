<template>
  <BasePlayer
    :previewImageLink="previewImageLink"
    :link="link"
    :progress="progress"
    title="Buttons W and S can change speed of your player"
    @pause="pause"
  />
</template>

<script setup lang="ts">
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
})

function pause(currentTime) {
  emit('pause', currentTime)
}
</script>
