
<script setup lang="ts">
defineProps<{
  name: string
  projectCount: number
}>()
</script>

<template>
  <div class="skill-item" tabindex="0">
    <span class="skill-name">{{ name }}</span>

    <div class="skill-details">
      <span>
        Used in {{ projectCount }}
        {{ projectCount === 1 ? 'project' : 'projects' }}
      </span>
    </div>
  </div>
</template>

<style scoped>
.skill-item {
  display: flex;
  flex-direction: column;
  padding: 10px 14px;
  background: #191c23;
  border: 1px solid #292d35;
  border-radius: 5px;
  cursor: default;
  transition:
    background 0.2s,
    border-color 0.2s;
}

.skill-name {
  color: #c6d0df;
  font-size: 0.9rem;
  white-space: nowrap;
}

.skill-details {
  display: grid;
  grid-template-rows: 0fr;
  opacity: 0;
  transition:
    grid-template-rows 0.25s ease,
    opacity 0.2s ease;
}

.skill-details span {
  overflow: hidden;
  color: #8b9bb4;
  font-size: 0.75rem;
  white-space: nowrap;
}

.skill-item:hover,
.skill-item:focus-visible {
  background: #222630;
  border-color: #657b9d;
}

.skill-item:hover .skill-details,
.skill-item:focus-visible .skill-details {
  grid-template-rows: 1fr;
  opacity: 1;
}
</style>
