<template>
    <div class="card">
        <div class="value">
            {{ props.array.header }}: {{ props.array.value }}%
        </div>
        <div class="disc" :style="props.array.style">

        </div>
    </div>
</template>
<script lang="ts">
export default {
    props: ['array'],
    setup(props) {
        return {
            props
        }
    }
}
</script>
<style scoped>
.disc {
    margin: 2%;
    transition: opacity 0.5s;
    position: relative;
    top: -20%;
    display: flex;
    justify-content: center;
    padding-top: 80%;
    align-items: center;
    text-align: center;
    color: rgba(185, 184, 184, 0.877);
    opacity: 1;
    background-size: contain;
    width: 100%;
    height: 100%;
}


.value {
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    font-weight: 100;
    font-size: larger;
    background-position: center;
    position: relative;
    top: 45%;
    opacity: 0;
    color: rgb(233, 202, 202);
    transition: opacity 0.5s;
}

.value:hover {
    opacity: 1;
}



.disc:hover {
    opacity: 0.05;
    cursor: pointer;
}

.card:hover .value {
    opacity: 1;
}

.card {
    justify-content: center;
    align-items: center;
    text-align: center;
    background-size: cover;
    flex-direction: row;
    flex-wrap: wrap;
    display: flex;
    width: 150px !important;
    height: 150px !important;
}
</style>    