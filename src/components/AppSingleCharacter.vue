<script>

export default {
    name: "AppSingleCharacter",
    props: ["info"]
}
</script>

<template>
    <div class="cards">
        <img :src="info.image" alt="">
        <div class="text-cards">
            <div>
                <span>Nome:</span>
                {{ info.name }}
            </div>
            <div class="text-card">
                <span>Status:</span>
                {{ info.status }}
            </div>
            <div class="text-card">
                <span>Species:</span>
                {{ info.species }}
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables.scss' as *;
@use '../style/general.scss' as *;

.cards {
    text-align: center;
    line-height: 30px;
    border: 1px solid black;
    border-radius: 20px;
    padding: 20px 0;

    &:nth-child(6),
    &:nth-last-child(1) {
        width: 20%;

        img {
            width: 70%;
        }
    }

    img {
        width: 70%;
        border-radius: 50%;

        &:hover {
            box-shadow: 0 0 50px (rgb(0, 0, 0));
            cursor: pointer;
        }
    }

    .text-cards {
        padding: 10px 20px;
        text-align: left;

        h2 {
            color: white;
            font-size: 30px;
        }

        .text-card {
            font-size: 17px;
        }
    }

    span {
        color: rgb(255, 255, 255);
        font-size: 15px;
    }
}
</style>