<template>
    <div class="card">
        <div class="image">
            <v-carousel hide-delimiters show-arrows="hover" hide-delimiter-background class="vvv">
                <v-carousel-item v-for="(item, i) in items.img" :key="i" :src="item.src" cover>
                </v-carousel-item>
            </v-carousel>
        </div>
        <div class="disc">
            <div class="header">{{ items.header }}</div>
            {{ items.desc}}
        </div>
    </div>
</template>
<script lang="ts">
export default {
    props: ['items'],
    setup(props) {
        return {
            items: props.items
        }
    }
}
</script>
<style scoped>
.vvv {
    height: 300px !important;
}

.header {
    color: aliceblue;
    font-size: 140%;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.disc {
    color: rgba(255, 255, 255, 0.774);
    text-align: center;
    height: 10%;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    opacity: 0;
    transition: opacity 0.7s;
    /* font-weight: 100; */
}

.image {
    /* background-image: url('../assets/c-o-season-9-splash-warwick.jpg'); */
    height: 300px;
    width: 100%;
    border-radius: 1%;
    background-size: cover;
    overflow: hidden;
    transition: all 0.5s;
    /* transition: width 0.5s; */
    position: relative;
    scale: 1;
    top: 0px;
}

.image:hover+.disc {
    opacity: 1;
}

.image:hover {
    top: -30px;
    cursor: pointer;
    opacity: 1;
    scale: 1.05;
}

.disc:hover {
    top: -30px;
    cursor: pointer;
    opacity: 1;
    padding: 3px;
}

.card {
    padding: 0px;
    margin: 0px;
    border-top-left-radius: 2%;
    border-top-right-radius: 2%;
    border-width: 5px;
    border-style: double;
    border-color: #6d6a6a;
    width: 50%;
    height: 100%;

}
</style>