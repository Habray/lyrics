<script setup>
const props = defineProps({
  id: String
})
</script>

<template>
  <div class="songs-number">{{ id.replace(/^0+/, '') }}</div>
</template>

<style scoped>
.songs-number {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #66bb6a;
  height: 50px;
  width: 50px;
  border-radius: 50%;
  font-size: 24px;
  font-weight: 600;
  color: var(--primary-bg);
}
</style>
