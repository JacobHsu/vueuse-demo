<template>
  <div>
    <h1>{{ msg }}</h1>
    <button @click="clickedFn">Smash me!</button>
    <note>Delay is set to 2000ms for this demo.</note>

    <p>Button clicked: {{ clicked }}</p>
    <p>Event handler called: {{ updated }}</p>
  </div>
</template>

<script lang="ts">
// https://vueuse.org/shared/usethrottlefn/
import { ref, defineComponent } from 'vue';
import { useThrottleFn } from '@vueuse/core';
export default defineComponent({
  name: 'UseThrottleFn',
  props: {
    msg: {
      type: String,
      required: true,
    },
  },
  setup: () => {
    const updated = ref(0);
    const clicked = ref(0);
    const throttledFn = useThrottleFn(() => {
      updated.value += 1;
    }, 2000);
    const clickedFn = () => {
      clicked.value += 1;
      throttledFn();
    };
    return { updated, clicked, clickedFn };
  },
});
</script>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
