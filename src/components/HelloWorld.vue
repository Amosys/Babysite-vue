<script setup lang="ts">
import { assertExpressionStatement, awaitExpression } from '@babel/types';
import axios from 'axios'

defineProps<{
  msg: string
}>()
</script>

<script lang="ts">
export default {
  data() {
    return {
    name: 'helloworld'
    }
  }, 
  methods: {
    onBtnClick() {
      console.log('clicked')
      axios.get('http://web_network/api/hello').then((function (response) {
        console.log(response);
      }))
    }
  }
}
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h3>
      You’ve successfully created a project with
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>. What's next?
    </h3>
    <button @click="onBtnClick()">click</button>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
