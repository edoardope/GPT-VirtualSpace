<script>
import SetUpMenu from './components/SetUpMenu.vue';
import WorldSetUp from './components/WorldSetUp.vue';
import MainMenu from './components/MainMenu.vue';
import { store } from './store.js';

export default {
  name: "App",
  components: {
    SetUpMenu,
    WorldSetUp,
    MainMenu
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getImagePath: function (imgPath) {
      return new URL(imgPath, import.meta.url).href;
    }
  }
}
</script>

<template>
  <SetUpMenu v-if="store.currentScreen == 'SetUpMenu'"/>
  <WorldSetUp v-if="store.currentScreen == 'WorldSetUp'"/>
  <MainMenu v-if="store.currentScreen == 'MainMenu'"/>
</template>

<style lang="scss">
@use 'style/main.scss' as *;
</style>
