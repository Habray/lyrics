<script setup>
import { ref } from 'vue'
import lyrics from '@/assets/lyrics.json'
const lyricsData = ref(lyrics)
</script>

<template>
  <div class="filters small-container-padding">
    <div class="search-bar">
      <form @click.prevent="">
        <input type="text" name="" id="" placeholder="Search" />
        <button type="submit">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            x="0px"
            y="0px"
            width="30"
            height="30"
            viewBox="0 0 50 50"
          >
            <path
              d="M 21 3 C 11.601563 3 4 10.601563 4 20 C 4 29.398438 11.601563 37 21 37 C 24.355469 37 27.460938 36.015625 30.09375 34.34375 L 42.375 46.625 L 46.625 42.375 L 34.5 30.28125 C 36.679688 27.421875 38 23.878906 38 20 C 38 10.601563 30.398438 3 21 3 Z M 21 7 C 28.199219 7 34 12.800781 34 20 C 34 27.199219 28.199219 33 21 33 C 13.800781 33 8 27.199219 8 20 C 8 12.800781 13.800781 7 21 7 Z"
            ></path>
          </svg>
        </button>
      </form>
    </div>
    <div class="sorting">
      <p class="total-songs--text">
        Songs <span>{{ lyricsData.length }}</span>
      </p>
    </div>
  </div>
  <div class="list-container">
    <ul>
      <li v-for="song in lyricsData" :key="song.id" class="big-container-padding">
        <router-link :to="{ name: 'detail', params: { id: song.id } }">
          <div class="songs-number">{{ song.id.replace(/^0+/, '') }}</div>
          <div class="songs-detail">
            <h4 class="songs-title">{{ song.title }}</h4>
            <p class="songs-description">{{ song.tags[0] }}</p>
          </div>
        </router-link>
      </li>
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
.songs-detail .songs-title {
  font-size: 20px;
  line-height: normal;
  color: white;
  text-transform: capitalize;
}
.songs-detail .songs-description {
  font-size: 16px;
  line-height: normal;
  color: #a8a8a8;
  text-transform: capitalize;
}
</style>
