<script>

export default {
    name: "AppSingleCharacter",
    props: ["info"]
}
</script>

<template>
    <div class="cards">
        <img :src="info.image" alt="">
        <h2>{{ info.name }}</h2>
        <div class="text-card">{{ info.status }}</div>
        <div class="text-card">{{ info.species }}</div>
    </div>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables.scss' as *;
@use '../style/general.scss' as *;

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
        width: 85%;
        border-radius: 50%;

        &:hover {
            box-shadow: 0 0 50px (rgb(0, 0, 0));
            cursor: pointer;
        }
    }
}
</style>