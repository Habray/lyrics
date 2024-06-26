<script setup>
import { computed } from 'vue'
import { RouterLink, RouterView } from 'vue-router'
import { useRoute } from 'vue-router'
import IconHamberger from '@/components/icons/IconHamberger.vue'
import IconChevronRight from '@/components/icons/IconChevronRight.vue'

const route = useRoute()
const isHomeRoute = computed(() => route.name === 'home')
</script>

<template>
  <div class="screen">
    <header>
      <div class="notification-bar"><img src="@/assets/notification-bar.jpg" /></div>

      <div class="nav-top-container big-container-padding">
        <router-link :to="{ name: 'home' }">
          <div v-if="isHomeRoute">
            <IconHamberger />
          </div>

          <div v-else>
            <IconChevronRight />
          </div>
        </router-link>
        <h1 class="nav-heading--text">Lyrics</h1>
      </div>

      <!-- <div class="wrapper">
        <nav>
          <RouterLink to="/">Home</RouterLink>
        </nav>
      </div> -->
    </header>

    <RouterView />
  </div>
</template>

<style scoped>
.notification-bar {
  display: flex;
}
.notification-bar img {
  object-fit: contain;
  height: auto;
  width: 100%;
}
.nav-top-container {
  background-color: var(--primary-bg);
  display: flex;
  align-items: center;
  column-gap: 40px;
}
.nav-top-container a > div {
  display: flex;
  align-items: center;
}

svg.nav-icon {
  height: auto;
  width: 100%;
  max-width: 1.6rem;
}
.nav-heading--text {
  font-size: 26px;
  line-height: normal;
  color: white;
}

nav a {
  padding: 5px 10px;
  font-size: 20px;
}
nav a:first-child {
  padding-left: 0;
}
nav a:last-child {
  padding-right: 0;
}
</style>
