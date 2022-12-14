<script>
export default {
    name: "AppHeader",
    props: ["msg"]
}
</script>

<template>
    <section class="container">
        <h1>
            {{ msg }}
        </h1>
    </section>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables.scss' as *;
@use '../style/general.scss' as *;

.container {

    h1 {
        text-align: center;
        font-size: 50px;
    }

}
</style>