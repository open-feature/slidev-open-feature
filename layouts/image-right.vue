<script setup lang="ts">
defineProps<{
  image: string
  class?: string
}>()
</script>

<template>
  <div class="slidev-layout image-right wave-bg">
    <div class="content">
      <slot />
    </div>
    <div
      class="image-container"
      :style="{ backgroundImage: `url('${image}')` }"
    />
  </div>
</template>
