<script setup lang="ts">
/**
 * Presenter Profile Component
 *
 * Displays a presenter's photo (or initials fallback), name, and company.
 * Designed to be placed inline on any slide.
 *
 * @prop {string} name - Presenter's full name (required).
 * @prop {string} company - Company or organization name.
 * @prop {string} photo - URL or path to the presenter's photo.
 * @prop {string} size - Diameter of the avatar circle. Defaults to '80px'.
 */

import { computed } from 'vue'

const props = withDefaults(
  defineProps<{
    name: string
    company?: string
    photo?: string
    size?: string
  }>(),
  {
    size: '80px',
  },
)

const initials = computed(() => {
  return props.name
    .split(/\s+/)
    .filter(Boolean)
    .map((word) => word[0].toUpperCase())
    .slice(0, 2)
    .join('')
})
</script>

<template>
  <div class="presenter-profile" role="group" :aria-label="`Presenter: ${name}`">
    <div
      class="presenter-avatar"
      :style="{ width: size, height: size, minWidth: size, fontSize: `calc(${size} * 0.38)` }"
    >
      <img
        v-if="photo"
        :src="photo"
        :alt="`Photo of ${name}`"
        class="presenter-avatar-img"
      />
      <span v-else class="presenter-avatar-initials" aria-hidden="true">
        {{ initials }}
      </span>
    </div>

    <div class="presenter-info">
      <span class="presenter-name">{{ name }}</span>
      <span v-if="company" class="presenter-company">{{ company }}</span>
    </div>
  </div>
</template>

<style scoped>
.presenter-profile {
  display: inline-flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
}

.presenter-avatar {
  border-radius: 50%;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: var(--of-accent-purple);
  flex-shrink: 0;
}

.presenter-avatar-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.presenter-avatar-initials {
  color: #ffffff;
  font-weight: 600;
  line-height: 1;
  user-select: none;
}

.presenter-info {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.15rem;
}

.presenter-name {
  font-weight: 600;
  color: var(--of-text);
  line-height: 1.3;
}

.presenter-company {
  color: var(--of-text-muted);
  font-size: 0.85em;
  line-height: 1.3;
}
</style>
