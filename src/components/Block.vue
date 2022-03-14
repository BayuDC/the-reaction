<script>
export default {
    name: "Block",
    props: ["delay"],
    methods: {
        start() {
            this.reactime = Date.now();
        },
        stop() {
            this.reactime = Date.now() - this.reactime;
            console.log(this.reactime);
        },
    },
    data() {
        return {
            show: false,
            reactime: 0,
        };
    },
    mounted() {
        setTimeout(() => {
            this.show = true;
            this.start();
        }, this.delay);
    },
};
</script>

<template>
    <div v-if="show" @click="stop" class="block">Click Me</div>
</template>

<style>
.block {
    color: #fff;
    background: rgb(65, 184, 131);
    max-width: 400px;
    height: 200px;
    margin: 60px auto;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
}
</style>