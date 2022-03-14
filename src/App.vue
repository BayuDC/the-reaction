<script>
export default {
    name: "App",
    components: {},
    methods: {
        start() {
            this.playing = true;
        },
    },
    data() {
        return {
            playing: false,
        };
    },
};
</script>

<template>
    <h1>The Reaction Game</h1>
    <button @click="start">Start</button>
</template>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: rgb(52, 73, 94);
    margin-top: 60px;
}
#app button {
    font-size: 16px;
    border: none;
    background: rgb(65, 184, 131);
    color: white;
    padding: 10px 20px;
}
</style>
