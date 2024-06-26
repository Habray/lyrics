<script setup>
import { onMounted, ref } from 'vue'
import lyrics from '@/assets/lyrics.json'
import TagComponent from '@/components/TagComponent.vue'
import SongNumberComponent from '@/components/SongNumberComponent.vue'
import SongTitleComponent from '@/components/SongTitleComponent.vue'
import IconSearch from '@/components/icons/IconSearch.vue'
const lyricsData = ref(lyrics)
const searchText = ref('')
let filterdSearch = ref([])
function searchFilter() {
  if (!isNaN(parseInt(searchText.value))) {
    filterdSearch.value = lyrics.filter((song) => song.id.replace(/^0+/, '') === searchText.value)
  } else {
    const lowerSearchText = searchText.value.toLowerCase()
    filterdSearch.value = lyrics.filter(
      (song) =>
        song.title.toLowerCase().includes(lowerSearchText) ||
        song.lyrics.toLowerCase().includes(lowerSearchText)
    )
  }
}

onMounted(() => {
  filterdSearch.value = lyricsData.value
})
</script>

<template>
  <div class="filters small-container-padding">
    <div class="search-bar">
      <form @keyup.prevent="searchFilter" @submit.prevent="searchFilter">
        <input type="text" v-model="searchText" id="" placeholder="Search" />
        <button type="submit">
          <IconSearch />
        </button>
      </form>
    </div>
    <div class="sorting">
      <p class="total-songs--text">
        Songs <span>{{ filterdSearch.length }}</span>
      </p>
    </div>
  </div>
  <div class="list-container">
    <ul>
      <li v-for="song in filterdSearch" :key="song.id" class="big-container-padding">
        <router-link :to="{ name: 'detail', params: { id: song.id } }">
          <SongNumberComponent :id="song.id" />
          <div class="songs-detail">
            <SongTitleComponent :title="song.title" />
            <TagComponent :tag="song.tags" />
          </div>
        </router-link>
      </li>
      <p v-if="!filterdSearch.length" class="not-found">No Song Found</p>
    </ul>
  </div>
</template>

<style scoped>
.filters {
  background-color: var(--secondary-bg);
}

.search-bar form {
  display: flex;
  flex-wrap: wrap;
  position: relative;
}
.search-bar form input {
  flex: 1;
  padding: 15px 10px;
  border-radius: 8px;
  border: 0;
  font-size: 18px;
}
.search-bar form button {
  position: absolute;
  right: 5px;
  top: 50%;
  transform: translateY(-50%);
  height: 100%;
  border: 0;
  background-color: transparent;
}
.sorting {
  display: flex;
  justify-content: end;
  align-items: center;
  padding: 5px 0;
}

.total-songs--text {
  font-size: 16px;
  color: #a8a8a8;
}

.total-songs--text span {
  font-size: 20px;
  font-weight: 600;
  color: #5ca460;
}
.list-container {
  background-color: var(--primary-bg);
  overflow-y: scroll;
  scrollbar-width: none;
  height: 485px;
}
ul {
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
}
ul li a {
  display: grid;
  align-items: center;
  grid-template-columns: 1fr 4fr;
}
ul li:hover {
  background-color: #303030;
}
.not-found {
  font-size: 16px;
  color: #e95b5b;
  text-align: center;
}
</style>
