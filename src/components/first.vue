<template>
  <div class="screen" @scroll="scroll">
    <div class="color " id="last" v-if="contain">
      <v-img src='' class="image bg-grey-lighten-2" conten>
      </v-img>
      <div class="header">Hi, I'm Hamza</div>
      <div class="disc1">
        I Write About Building Products AS a Front-End Developer</div>
      <div class="disc2">
        <div>I'm building an analytics SaaS called Affilimate and a newsletter and</div>
        <div>To See My <a href="">CV→</a> </div>
      </div>
    </div>

  </div>
</template>

<script lang='ts'>

import { defineComponent } from 'vue'
import { gsap } from 'gsap';
export default defineComponent({
  name: 'HelloWorld',
  data() {
    return {
      start: false,
      contain: true,
      top: 0
    }
  },
  methods: {
    scroll() {
      window.scroll({
        top: 800,
        left: 0,
        behavior: 'smooth'
      });
    }
    ,
    show() {
      this.contain = true
      setTimeout(() => gsap.fromTo("#last", { scale: 0.5, opacity: 0 }, { scale: 1, duration: 1.5, opacity: 1 }), 0.1)
    }

  },
  created() {
    setTimeout(() => this.show(), 10)
  }
}
)
</script>
<style scoped>
a {
  color: rgb(255, 255, 255);
  font-family: Georgia, 'Times New Roman', Times, serif;
  font-weight: 100;
  font-size: larger;
}

.header {
  font-size: 350%;
  font-weight: 500;
  padding-bottom: 0%;
  margin-bottom: 0%;
}

.disc2 {
  margin-top: 5%;
  font-weight: 100;

}

.disc1 {
  padding-top: 0%;
  margin-top: 0%;
  font-size: 130%;
  font-weight: 100;
  font-family: Verdana, Geneva, Tahoma, sans-serif
}

.image {
  margin-left: 32%;
  width: 200px;
  height: 200px;
  border-radius: 100%;
  background-image: url('../assets/hamza.jpg');
  background-size: 100%;
}


.show {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: row;
  gap: 5%;
}

.screen {
  background-image: url('../assets/portfoliobg.png');
  background-size: cover;
  flex-direction: row;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  height: 35%;
  width: 100%;
  background-color: rgb(9, 10, 11);
}

.box {
  color: #d1d1d1;
  font-weight: 300;
  font-size: xx-large;
  font-family: serif;

}

.color {
  height: 60%;
  width: 50%;
  color: #d1d1d1;
}

.class1 {
  color: rgb(255, 196, 0);
}

.class2 {
  color: blue;
}

.orange {
  color: rgba(209, 209, 209, 0.959);
}

.btn {
  background-color: #9b9999;
}
</style>
