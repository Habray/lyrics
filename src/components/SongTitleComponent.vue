<script setup>
const props = defineProps({
  title: String
})
</script>

<template>
  <h4 class="songs-title">{{ title }}</h4>
</template>

<style scoped>
.songs-title {
  font-size: 20px;
  line-height: normal;
  color: white;
  text-transform: capitalize;
}
</style>
