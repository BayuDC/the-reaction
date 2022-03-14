<script>
export default {
    name: "Block",
    props: ["delay"],
    data() {
        return {
            show: false,
        };
    },
    mounted() {
        setTimeout(() => {
            this.show = true;
        }, this.delay);
    },
};
</script>

<template>
    <div v-if="show" class="block">Click Me</div>
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