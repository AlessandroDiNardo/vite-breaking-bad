<script>
import axios from 'axios'
import AppHeader from './components/AppHeader.vue';
import AppCharacterList from './components/AppCharacterList.vue';
import AppSearch from './components/AppSearch.vue';
import { store } from './store.js';

export default {
  name: "App",
  components: {
    AppHeader,
    AppCharacterList,
    AppSearch
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCharactersList() {

      let myURL = store.apiURL;

      if (store.searchStatus !== "") {
        myURL += `?${store.apiStatus}=${store.searchStatus}`;
      }

      axios
        .get(myURL)
        .then(res => {
          store.characterList = res.data.results;
        })
        .catch(err => {
          console.log("ERRORI", err);
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
    <AppSearch @search="getCharactersList()" />
    <AppCharacterList />
  </main>
</template>

<style lang="scss">
@use './style/partials/variables.scss' as *;
@use './style/general.scss' as *;
</style>
