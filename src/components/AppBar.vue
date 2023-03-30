<template>
  <nav class="my_nav d-none d-md-block">
    <v-container class="fill-height d-flex justify-space-between align-center">
      <div class="logo">
        <a href="#" target="_blank_">
          <img src="../assets/l.jpg" color="#fff" width="100" alt="logo" />
        </a>
      </div>
      <div class="links">
        <a
          class="link text-decoration-none white--text"
          v-for="(items, i) in links"
          :key="i"
          href="items.url"
        >
          <span class="white underline_left"></span>
          {{ items.title }}
          <span class="white underline_right"></span>
        </a>
      </div>
      <div class="action_btn"><button class="btn">Download App</button></div>
    </v-container>
  </nav>
  <nav
    class="my_nav d-md-none"
    style="position: absolute; top: 0px; width: 100%"
  >
    <v-container class="fill-height d-flex justify-space-between align-center">
      <div class="logo">
        <a href="#" target="_blank_">
          <img src="../assets/l.jpg" color="#fff" width="100" alt="logo" />
        </a>
      </div>
      <div class="links">
        <a
          class="link text-decoration-none white--text"
          v-for="(items, i) in links"
          :key="i"
          href="items.url"
        >
          <span class="white underline_left"></span>
          <i :class="items.icon"></i>
          <span class="white underline_right"></span>
        </a>
      </div>

      <div class="action_btn"><button class="btn">Download App</button></div>
    </v-container>
  </nav>
</template>


<style scoped>
@import url("https://fonts.cdnfonts.com/css/event-horizon");
* {
  margin: 0;
  padding: 0;
  text-decoration: none;
  font-family: "Event Horizon", sans-serif;
}
.my_nav {
  backdrop-filter: blur(10px);
  background: #000;
}
.link {
  padding: 10px 20px;
  position: relative;
  color: #ffffff;
}
.btn {
  position: relative;
  border: none;
  background: #fff1;
  backdrop-filter: blur(10px);
  color: rgb(255, 255, 255);
  padding: 10px 20px;
  letter-spacing: 2px;
  text-transform: uppercase;
  overflow: hidden;
  border: 1px solid #fff5;
  border-radius: 1px;
  transition: 0.25s;
}
.btn:hover {
  box-shadow: 5px 5px 5px #0005;
  transform: scale(1.025);
}
.btn:active {
  box-shadow: 0 0 0 #0005;
  transform: scale(1);
}
.btn::before {
  position: absolute;
  content: "";
  height: 100%;
  width: 100%;
  background: -webkit-linear-gradient(
    left,
    rgba(255, 255, 255, 0) 0,
    rgba(255, 255, 255, 0.25) 50%,
    transparent 50%
  );
  top: 0;
  left: -80%;
  transform: skew(-45deg);
  transition: 0.5s;
}
.btn:hover::before {
  left: 120%;
}
</style>

<script setup>
import { ref } from "vue";
let links = ref([
  {
    url: "#",
    title: "Home",
  },
  {
    url: "#",
    title: "About",
  },
  {
    url: "#",
    title: "Service",
  },
  {
    url: "#",
    title: "Contact",
  },
]);
</script>