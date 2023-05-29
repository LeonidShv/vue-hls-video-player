<template>
  <VDefaultVideoPlayer
    v-if="type === 'default'"
    @pause="pause"
    :previewImageLink="previewImageLink"
    :link="link"
    :progress="progress"
    :isMuted="isMuted"
    :isControls="isControls"
  />

  <VPreviewVideoPlayer
    v-else-if="type === 'preview'"
    :previewImageLink="previewImageLink"
    :link="link"
  />
</template>

<script setup>
import VDefaultVideoPlayer from './VDefaultVideoPlayer.vue'
import VPreviewVideoPlayer from './VPreviewVideoPlayer.vue'

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
  type: {
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
