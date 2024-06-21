<script setup>
import { ref } from 'vue'
const lyricsData = ref([
  {
    id: '001',
    title: 'Sunset Dreams',
    tags: ['Dreams', 'Hope', 'Acoustic', 'Folk'],
    lyrics:
      'As the sun sets low\nAnd the stars begin to glow\nDreams take flight in the night\nGuided by the moonlight'
  },
  {
    id: '002',
    title: 'Whispering Winds',
    tags: ['Nature', 'Calm', 'Instrumental', 'Ambient'],
    lyrics:
      'Whispering winds through the trees\nCarrying tales on the breeze\nSoftly spoken, secrets shared\nIn the quiet evening air'
  },
  {
    id: '003',
    title: 'Ocean Waves',
    tags: ['Sea', 'Relaxation', 'Instrumental', 'Calm'],
    lyrics:
      "Waves crashing on the shore\nA melody we can't ignore\nRhythmic dance, ebb and flow\nNature's song, a soothing show"
  },
  {
    id: '004',
    title: 'Mountain High',
    tags: ['Adventure', 'Inspiration', 'Acoustic', 'Folk'],
    lyrics:
      'Climbing mountains, reaching high\nTouch the clouds, kiss the sky\nEvery step, a journey new\nWith the peak in clear view'
  },
  {
    id: '005',
    title: 'City Lights',
    tags: ['Urban', 'Night', 'Pop', 'Dance'],
    lyrics:
      'City lights, shining bright\nNeon signs, in the night\nHeartbeat quickens with the beat\nDancing in the busy street'
  },
  {
    id: '006',
    title: 'Rainy Day',
    tags: ['Rain', 'Relaxation', 'Instrumental', 'Ambient'],
    lyrics:
      'Raindrops fall, soft and light\nCreating music through the night\nPitter-patter on the ground\nA soothing, calming sound'
  },
  {
    id: '007',
    title: 'Summer Breeze',
    tags: ['Summer', 'Relaxation', 'Acoustic', 'Folk'],
    lyrics:
      'Summer breeze, warm and kind\nMemories in the sunshine\nLazy days and starry nights\nEverything feels so right'
  },
  {
    id: '008',
    title: 'Under the Stars',
    tags: ['Night', 'Calm', 'Acoustic', 'Folk'],
    lyrics:
      'Under the stars, we find our place\nIn the quiet, in the space\nWhispers of the universe\nIn the silence, we immerse'
  },
  {
    id: '009',
    title: 'Forest Path',
    tags: ['Nature', 'Adventure', 'Acoustic', 'Folk'],
    lyrics:
      "Walking down the forest path\nLeaves crunch softly, nature's bath\nBirds sing sweetly, all around\nIn this haven, peace is found"
  },
  {
    id: '010',
    title: "Journey's End",
    tags: ['Journey', 'Hope', 'Acoustic', 'Folk'],
    lyrics:
      'Every road leads to an end\nWhere the heart and spirit mend\nLessons learned and stories told\nIn our hearts, we hold them bold'
  }
])
</script>

<template>
  <div class="list-container">
    <ul>
      <li v-for="song in lyricsData" :key="song.id" class="big-container-padding">
        <div class="songs-number">{{ song.id }}</div>
        <div class="songs-detail">
          <h4 class="songs-title">{{ song.title }}</h4>
          <p class="songs-description">{{ song.tags[0] }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.list-container {
  background-color: var(--primary-bg);
  overflow-y: scroll;
  scrollbar-width: none;
  height: 460px;
}
ul {
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 10px;
}
ul li {
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
