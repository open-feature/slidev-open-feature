<script setup lang="ts">
defineProps<{
  image: string
  class?: string
}>()
</script>

<template>
  <div class="slidev-layout image-left wave-bg">
    <div
      class="image-container"
      :style="{ backgroundImage: `url('${image}')` }"
    />
    <div class="content">
      <slot />
    </div>
  </div>
</template>
