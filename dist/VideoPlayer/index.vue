<template>
  <VDefaultVideoPlayer
    v-if="type === 'default'"
    @pause="pause"
    :previewImageLink="previewImageLink"
    :link="link"
    :progress="progress"
    class="course-video"
  />

  <VPreviewVideoPlayer
    v-else-if="type === 'preview'"
    class="course-video"
    :previewImageLink="previewImageLink"
    :link="link"
  />
</template>

<script setup lang="ts">
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
})

function pause(currentTime) {
  emit('pause', currentTime)
}
</script>
