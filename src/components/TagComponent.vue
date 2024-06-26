<script setup>
const props = defineProps({
  tag: Array
})
</script>

<template>
  <p class="songs-description">{{ tag.join(', ') }}</p>
</template>

<style scoped>
.songs-description {
  font-size: 14px;
  line-height: normal;
  color: #a8a8a8;
  text-transform: capitalize;
}
</style>
