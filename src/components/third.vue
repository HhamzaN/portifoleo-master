<template>
    <div class="all">
        <div class="header" id="work">My Work</div>
        <div class="screen">
            <card :items="ix[i]" v-for="(item, i) in ix" key="i" id="workImage" class="card"></card>
        </div>
    </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue'
import card from './card.vue'
import { gsap } from 'gsap'
export default defineComponent({
    components: {
        card
    },
    setup() {
        window.addEventListener('scroll', (event) => {
            window.scrollY == 300 ? (headerWork()) : ''
            window.scrollY == 400 ? (imageWork()) : ''
        });
        function imageWork() {
            gsap.fromTo("#workImage", { y: -100 }, { y: 0, duration: 2, });
        }
        function headerWork() {
            gsap.fromTo("#work", { y: -100 }, { y: 0, scale: 3, duration: 2, });
        }
        let ix: Array<Object>;
        ix = [
            {
                desc: 'to create task and share this task with your frind or employ it make work more easy',
                header: 'Task Maneger',
                img:
                    [
                        { src: 'assets/task manager auth.PNG' },
                        { src: 'assets/task1.PNG' },
                        { src: 'assets/task2.PNG' }
                    ]
            }
            ,
            {
                desc: 'ham,za',
                header: 'SuperHeroes',
                img:
                    [
                        { src: 'assets/nj1.PNG' },
                        { src: 'assets/nj2.PNG' },
                        { src: 'assets/nj3.PNG' }
                    ],
            }
            , {
                desc: 'i work as frontend developer in accounting module in Minaret Center ',
                header: 'ERP System',
                img:
                    [
                        { src: 'assets/erp.jpg' },
                        { src: 'assets/1.png' },
                        { src: 'assets/2.png' },
                    ]
            },
            {
                desc: 'ham,za',
                header: 'Sama Scholl',
                img:
                    [
                        { src: 'assets/english1.PNG' },
                        { src: 'assets/english2.PNG' },
                        { src: 'assets/english3.PNG' }
                    ]
            },
            {
                desc: 'employ can creat new student and that studen can see bock and online lacture and more',
                header: 'Student Services',
                img:
                    [
                        { src: 'assets/Login.PNG' },
                        { src: 'assets/HomeDark.PNG' },
                        { src: 'assets/OrdersDark.PNG' }
                    ]
            },

        ]
        return {
            headerWork, imageWork, ix
        }
    }
})
</script>
<style scoped>
.card {
    width: 30%;
    height: 310px;
    transition: height 0.6s;
}

.card:hover {
    height: 400px;
}

.header {
    padding-top: 2%;

    margin-bottom: 10%;
    text-align: center;
    font-size: larger;
    font-weight: 100;
    font-family: 'Times New Roman', Times, serif;
    color: rgba(185, 184, 184, 0.877);
}

.all {
    background-color: rgb(18, 20, 22);
    height: 1000px;
    width: 100%;
    background-image: url('../assets/11.jpg');
    background-size: cover;
}

.screen {
    width: 100%;
    flex-wrap: wrap;
    gap: 15px;
    display: flex;
    justify-content: center;
}
</style>