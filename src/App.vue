<script>
import Block from "./components/Block.vue";

export default {
    name: "App",
    components: {
        Block,
    },
    methods: {
        start() {
            this.delay = 2000 + Math.random() * 3000;
            this.playing = true;
        },
        end(reactime) {
            this.delay = null;
            this.score = reactime;
            this.playing = false;
        },
    },
    data() {
        return {
            playing: false,
            delay: 0,
            score: 0,
        };
    },
};
</script>

<template>
    <h1>The Reaction Game</h1>
    <button @click="start" :disabled="playing" type="button">Start</button>
    <p v-if="!playing && delay == null">Reaction Time: {{ this.score }}ms</p>
    <p v-if="playing">Ready...</p>
    <Block v-if="playing" :delay="delay" @end="end"></Block>
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
    outline: none;
    cursor: pointer;
}
#app button:disabled {
    cursor: not-allowed;
}
</style>
