<script>
import { store } from '../store.js';

export default {
    name: "AppMain",
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
            <div class="cards">
                <img src="https://rickandmortyapi.com/api/character/avatar/1.jpeg" alt="">
                <h2>nome</h2>
                <div class="text-card">stato</div>
                <div class="text-card">specie</div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables.scss' as *;
@use '../style/general.scss' as *;

.container {

    .card-container {
        display: flex;
        flex-wrap: wrap;

        .cards {
            text-align: center;
            line-height: 30px;

            h2 {
                color: white;
                font-size: 30px;
            }


            .text-card {
                font-size: 17px;
            }

            img {
                border-radius: 50%;
            }
        }
    }
}
</style>