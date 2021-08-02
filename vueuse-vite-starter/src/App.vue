<template>
  <div id="app">
    <img src="./logo.svg" />
    <h1>
      Hello
      <a href="https://github.com/vuejs/vite" target="__blank">Vite</a> and
      <a href="https://github.com/vueuse/vueuse" target="__blank">VueUse</a>!
    </h1>

    <h3>Mouse: {{ x }} x {{ y }}</h3>
    <UseThrottleFn msg="Hello Vue 3 + TypeScript + Vite" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useMouse, useCounter } from '@vueuse/core';
import UseThrottleFn from './components/UseThrottleFn.vue';

export default defineComponent({
  name: 'App',
  components: {
    UseThrottleFn,
  },
  setup: () => {
    const { x, y } = useMouse();
    return { x, y };
  },
});
</script>

<style scoped>
html,
body,
h1,
h2,
h3,
p {
  font-family: 'Noto Serif', serif;
  user-select: none;
}

#app {
  text-align: center;
  color: rgba(0, 0, 0, 0.4);
}
img {
  width: 500px;
}
a {
  color: #41b883;
  text-decoration: none;
  cursor: pointer;
}
</style>
