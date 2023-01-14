<template>
    <div class="all">
        <div class="header" id="skill">Skill</div>
        <div class="screen">
            <skillC v-for=" (skill, i) in skillCard" key="i" :array="skill" id="skillImage" />
        </div>
    </div>
</template>
<script lang="ts">

import { defineComponent } from 'vue';
import skillC from './skillC.vue';
import { gsap } from 'gsap'
export default defineComponent({
    components: {
        skillC
    },
    setup() {
        window.addEventListener('scroll', (event) => {
            window.scrollY == 1200 ? (headerSkill()) : ''
            window.scrollY == 1300 ? (imageSkill()) : ''
        });
        let skillCard = [
            {
                header: 'HTML', style: "background-image: url('assets/Html-5-01.png');"
                , value: 90
            },
            {
                header: 'CSS', style: "background-image: url('assets/CSS-3-01.png');"
                , value: 65
            },
            {
                header: 'Javascript', style: "background-image: url('assets/Javascript-03.png');"
                , value: 70
            },
            {
                header: 'Vue', style: "background-image: url('assets/Vue.png');"
                , value: 70
            },

            {
                header: 'Vuetify', style: "background-image: url('assets/vuetify.png');"
                , value: 50
            },
            {
                header: 'Tailwind ', style: "background-image: url('assets/telwind.png');"
                , value: 50
            },
            {
                header: 'Quasar', style: "background-image: url('assets/quasar.png');"
                , value: 50
            },
            {
                header: 'Typescript', style: "background-image: url('assets/Typescript.png');"
                , value: 60
            },
            {
                header: 'Github', style: "background-image: url('assets/pngwing.com (2).png');"
                , value: 75
            },
            {
                header: 'GitLab', style: "background-image: url('assets/GitLab.png');"
                , value: 75
            },
            {
                header: 'PHP', style: "background-image: url('assets/php.png');"
                , value: 20
            },
            {
                header: 'Laravel', style: "background-image: url('assets/Laravel-04.png');"
                , value: 20
            }, {
                header: 'Computer Maintenance', style: "background-image: url('assets/computer-logos-6.png');"
                , value: 50
            },



        ]
        function headerSkill() {
            gsap.fromTo("#skill", { y: -100 }, { y: 0, scale: 3, duration: 2, });
        }
        function imageSkill() {
            gsap.fromTo("#skillImage", { y: -100 }, { scale: 0.75, y: 0, duration: 3, });
        }
        return {
            skillCard,
            headerSkill, imageSkill
        }
    }
})
</script>
<style scoped>
.card {
    width: 100%;
}

.header {
    margin-bottom: 7%;
    text-align: center;
    font-size: larger;
    font-weight: 100;
    font-family: 'Times New Roman', Times, serif;
    color: rgba(185, 184, 184, 0.877);
}

.all {
    padding-top: 4%;
    background-color: rgb(23, 25, 29);
    height: 45%;
    width: 100%;
    background-image: url('../assets/12.jpg');
    background-size: cover;
    background-repeat: no-repeat;
}

.screen {
    text-align: center;
    justify-content: center;
    align-items: center;
    width: 100%;
    flex-wrap: wrap;
    gap: 15px;
    display: flex;
    padding-left: 15%;
    padding-right: 15%;

}
</style>