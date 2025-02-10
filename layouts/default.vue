<template>
  <div class="min-h-screen bg-fixed bg-base bg-graphing dark:bg-graph-dark; w-screen">
    <nav class="nav-container">
      <a class="mx-auto flex flex-col md:flex-row md:flex-grow">
        <menu-icon
          @click="menu = !menu"
          class="menu-toggle"
        />
        <img class="nav-logo" src="static/Ffish.png" />
        <span class="nav-title">Gunn Math Competition</span>
      </a>
      <div
        :class="menu ? 'max-h-96' : 'max-h-0 md:max-h-full'"
        class="nav-menu"
      >
        <a
          v-for="link of ['registration', 'format', 'schedule', '']"
          :key="link"
          :href="'/#' + (link==='home'?'':link)"
          class="menu-link"
        >
          {{ link }}
        </a>
        <div class="social-icons" id="social-icons">
          <a target="_blank" class="social-icon" href="https://gunnmathcircle.org">
            <home-icon class="h-5 w-auto" />
          </a>
          <a target="_blank" class="social-icon" href="https://discord.gg/wT3hFRbrzq">
            <img class="social-img dark:hidden h-6" src="/Discord-Logo-Black.png" />
            <img class="social-img hidden dark:inline-block h-6" src="/Discord-Logo-White.png" />
          </a>
          <a target="_blank" class="social-icon" href="https://github.com/GunnMath">
            <img class="social-img dark:hidden h-5" src="/GitHub-Mark-120px-plus.png" />
            <img class="social-img hidden dark:inline-block h-5" src="/GitHub-Mark-Light-120px-plus.png" />
          </a>
        </div>
      </div>
    </nav>
    <div class="content-wrapper">
      <Nuxt />
    </div>
  </div>
</template>

<script>
import { MenuIcon } from "vue-feather-icons";
import { HomeIcon } from "vue-feather-icons";

export default {
  components: {
    MenuIcon,
    HomeIcon,
  },
  data: () => ({
    menu: false,
  }),
};
</script>
