<template>
  <div>
    <v-app>
      <v-main class="">
        <first />
        <third></third>
        <skill />
      </v-main>
    </v-app>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import first from './components/first.vue'
import skill from './components/skill.vue'
import third from './components/third.vue'
export default defineComponent({
  name: 'App',
  components: {
    first,
    third,
    skill,
  },
  methods: {

  },
  data() {
    return {
      //
    }
  },
})
</script>
<style scoped>
.header {
  padding-top: 20px;
  text-align: center;
  font-size: larger;
  font-weight: 100;
  font-family: 'Times New Roman', Times, serif;
  color: rgba(185, 184, 184, 0.877);
}
</style>