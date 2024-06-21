<script setup>
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'

const totalNoOfSongs = ref(1696)
</script>

<template>
  <div class="screen">
    <header>
      <div class="notification-bar"><img src="@/assets/notification-bar.jpg" /></div>

      <div class="nav-top-container big-container-padding">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          x="0px"
          y="0px"
          width="50"
          height="50"
          viewBox="0,0,256,256"
          style="fill: #000000"
          class="hamgurger-icon"
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
        <h1 class="nav-heading--text">Lyrics</h1>
      </div>

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
            Songs <span>{{ totalNoOfSongs }}</span>
          </p>
        </div>
      </div>
      <div class="wrapper">
        <nav>
          <RouterLink to="/">Home</RouterLink>
        </nav>
      </div>
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

svg.hamgurger-icon {
  height: auto;
  width: 100%;
  max-width: 1.6rem;
}
.nav-heading--text {
  font-size: 26px;
  line-height: normal;
  color: white;
}

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
  color: #5ca460;
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
