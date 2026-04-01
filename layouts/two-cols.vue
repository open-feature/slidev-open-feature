<script setup lang="ts">
defineProps<{
  /**
   * Optional header content that spans both columns.
   * Use the default slot for left column and ::right:: for right column.
   */
  heading?: string
}>()
</script>

<template>
  <div class="slidev-layout two-cols wave-bg">
    <div v-if="$slots.header" class="two-cols-header">
      <slot name="header" />
    </div>
    <div class="col-left">
      <slot name="default" />
    </div>
    <div class="col-right">
      <slot name="right" />
    </div>
  </div>
</template>
