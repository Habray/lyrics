<script setup>
import { computed } from 'vue'
import { RouterLink, RouterView } from 'vue-router'
import { useRoute } from 'vue-router'

const route = useRoute()
const isHomeRoute = computed(() => route.name === 'home')
</script>

<template>
  <div class="screen">
    <header>
      <div class="notification-bar"><img src="@/assets/notification-bar.jpg" /></div>

      <div class="nav-top-container big-container-padding">
        <router-link :to="{ name: 'home' }">
          <svg
            v-if="isHomeRoute"
            xmlns="http://www.w3.org/2000/svg"
            x="0px"
            y="0px"
            width="50"
            height="50"
            viewBox="0,0,256,256"
            style="fill: #000000"
            class="nav-icon"
          >
            <g
              fill="#ffffff"
              fill-rule="nonzero"
              stroke="none"
              stroke-width="1"
              stroke-linecap="butt"
              stroke-linejoin="miter"
              stroke-miterlimit="10"
              stroke-dasharray=""
              stroke-dashoffset="0"
              font-family="none"
              font-weight="none"
              font-size="none"
              text-anchor="none"
              style="mix-blend-mode: normal"
            >
              <g transform="scale(5.12,5.12)">
                <path
                  d="M5,8c-0.72127,-0.0102 -1.39216,0.36875 -1.75578,0.99175c-0.36361,0.623 -0.36361,1.39351 0,2.01651c0.36361,0.623 1.0345,1.00195 1.75578,0.99175h40c0.72127,0.0102 1.39216,-0.36875 1.75578,-0.99175c0.36361,-0.623 0.36361,-1.39351 0,-2.01651c-0.36361,-0.623 -1.0345,-1.00195 -1.75578,-0.99175zM5,23c-0.72127,-0.0102 -1.39216,0.36875 -1.75578,0.99175c-0.36361,0.623 -0.36361,1.39351 0,2.01651c0.36361,0.623 1.0345,1.00195 1.75578,0.99175h40c0.72127,0.0102 1.39216,-0.36875 1.75578,-0.99175c0.36361,-0.623 0.36361,-1.39351 0,-2.01651c-0.36361,-0.623 -1.0345,-1.00195 -1.75578,-0.99175zM5,38c-0.72127,-0.0102 -1.39216,0.36875 -1.75578,0.99175c-0.36361,0.623 -0.36361,1.39351 0,2.01651c0.36361,0.623 1.0345,1.00195 1.75578,0.99175h40c0.72127,0.0102 1.39216,-0.36875 1.75578,-0.99175c0.36361,-0.623 0.36361,-1.39351 0,-2.01651c-0.36361,-0.623 -1.0345,-1.00195 -1.75578,-0.99175z"
                ></path>
              </g>
            </g>
          </svg>

          <svg
            v-else
            width="50"
            height="50"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 320 512"
            class="nav-icon"
          >
            <path
              fill="#ffffff"
              d="M9.4 233.4c-12.5 12.5-12.5 32.8 0 45.3l192 192c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L77.3 256 246.6 86.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0l-192 192z"
            />
          </svg>
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
.nav-top-container a {
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
