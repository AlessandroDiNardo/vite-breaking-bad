<script>
import AppSingleCharacter from './AppSingleCharacter.vue';

import { store } from '../store.js';

export default {
    name: "AppCharacterList",
    components: {
        AppSingleCharacter
    },
    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <section class="container">
        <div class="card-container">
            <AppSingleCharacter v-for="character in store.characterList" :key="character.id" :info="character" />
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables.scss' as *;
@use '../style/general.scss' as *;

.container {
    .card-container {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        gap: 50px;
    }
}
</style>