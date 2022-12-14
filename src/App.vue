<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './store.js';

export default {
  name: "App",
  components: {
    AppHeader,
    AppMain
  },
  data() {
    return {
      store,
    }
  },
}
</script>

<template>
  <header>
    <AppHeader :msg="store.title" />
  </header>
  <main>
    <AppMain />
  </main>
</template>

<style lang="scss">
@use './style/partials/variables.scss' as *;
@use './style/general.scss' as *;
</style>
