<script>

export default {
    data() {
        return {
        }
    },
}
</script>

<template>

<header>
    <div>
        <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/Yu-Gi-Oh%21.png" alt="yugioh logo">
    </div>
    <h1>Yu-Gi-Oh Api</h1>
</header>

</template>

<style lang="scss" scoped>
@use '../styles/partials/mixin' as *;
@use '../styles/partials/variable' as *;

header {
    display: flex;
    height: 10vh;
    img {
        width: 100%;
    }
}
</style>