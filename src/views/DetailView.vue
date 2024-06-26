<script setup>
import { computed, onMounted, reactive, ref } from 'vue'
import { useRoute } from 'vue-router'
import lyrics from '@/assets/lyrics.json'
import SongNumberComponent from '@/components/SongNumberComponent.vue'
import SongTitleComponent from '@/components/SongTitleComponent.vue'

const route = useRoute()
const song = reactive({ id: '', title: '', tags: [], lyrics: '' })

onMounted(() => {
  const songId = route.params.id
  const foundSong = lyrics.find((song) => song.id === songId)
  if (foundSong) {
    Object.assign(song, foundSong)
  }
})
const processedText = computed(() => {
  return song.lyrics.replace(/\n/g, '<br>')
})
</script>

<template>
  <div class="songs-detail">
    <div class="song-meta big-container-padding">
      <SongNumberComponent :id="song.id" />
      <SongTitleComponent :title="song.title" />
    </div>
    <div class="song-lyrics big-container-padding">
      <p v-html="processedText"></p>
    </div>
  </div>
</template>

<style scoped>
.song-meta {
  background-color: var(--secondary-bg);
  display: flex;
  align-items: center;
  gap: 10px;
}
.song-number {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #66bb6a;
  height: 50px;
  width: 50px;
  border-radius: 50%;
  font-size: 24px;
  font-weight: 600;
}
.song-title {
  flex: 5;
  font-size: 20px;
  line-height: normal;
  color: white;
  text-transform: capitalize;
}
.song-lyrics {
  border-top: 1px solid #303030;
  background-color: var(--primary-bg);
  height: 520px;
}
.song-lyrics p {
  font-size: 18px;
  line-height: normal;
  color: white;
}
</style>
