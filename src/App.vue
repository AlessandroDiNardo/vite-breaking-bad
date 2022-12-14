<script>
import axios from 'axios'
import AppHeader from './components/AppHeader.vue';
import AppCharacterList from './components/AppCharacterList.vue';
import AppSingleCharacter from './components/AppSingleCharacter.vue';

import { store } from './store.js';

export default {
  name: "App",
  components: {
    AppHeader,
    AppCharacterList,
    AppSingleCharacter,
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCharactersList() {
      axios
        .get(store.apiURL)
        .then(res => {
          store.characterList = res.data.results;
        })
        .catch(err => {
          console.lod("ERRORI", err);
        }

        );
    }
  },
  mounted() {
    this.getCharactersList();
  }
}
</script>

<template>
  <header>
    <AppHeader :msg="store.title" />
  </header>
  <main>
    <AppCharacterList />
  </main>
</template>

<style lang="scss">
@use './style/partials/variables.scss' as *;
@use './style/general.scss' as *;
</style>
