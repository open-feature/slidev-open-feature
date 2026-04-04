<script setup lang="ts">
/**
 * QR Code Component
 *
 * Generates and displays a QR code from a URL string.
 * Uses the `uqr` library to render client-side (no network dependency).
 *
 * @prop {string} url - The URL to encode in the QR code (required).
 * @prop {string} size - Width and height of the QR code. Defaults to '200px'.
 * @prop {string} color - Foreground color of the QR code. Defaults to '#000000'.
 * @prop {string} bgColor - Background color. Defaults to 'transparent'.
 */

import { computed } from 'vue'
import { encode } from 'uqr'

const props = withDefaults(
  defineProps<{
    url: string
    size?: string
    color?: string
    bgColor?: string
  }>(),
  {
    size: '200px',
    color: '#000000',
    bgColor: '#ffffff',
  },
)

const svgMarkup = computed(() => {
  try {
    const { data, size: moduleCount } = encode(props.url)
    const rects: string[] = []
    for (let y = 0; y < moduleCount; y++) {
      for (let x = 0; x < moduleCount; x++) {
        if (data[y][x]) {
          rects.push(`<rect x="${x}" y="${y}" width="1" height="1"/>`)
        }
      }
    }
    return [
      `<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 ${moduleCount} ${moduleCount}" shape-rendering="crispEdges">`,
      props.bgColor !== 'transparent'
        ? `<rect width="${moduleCount}" height="${moduleCount}" fill="${props.bgColor}"/>`
        : '',
      `<g fill="${props.color}">${rects.join('')}</g>`,
      `</svg>`,
    ].join('')
  } catch {
    return ''
  }
})
</script>

<template>
  <div
    class="qr-code-wrapper"
    :style="{ width: size, height: size }"
    :aria-label="`QR code for ${url}`"
    role="img"
    v-html="svgMarkup"
  />
</template>

<style scoped>
.qr-code-wrapper {
  display: inline-block;
  line-height: 0;
  border: 2px solid var(--of-text);
  border-radius: 8px;
  padding: 6px;
}

.qr-code-wrapper :deep(svg) {
  width: 100%;
  height: 100%;
}
</style>
