<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h3>Mouse: {{x}} x {{y}}</h3>
  </div>
</template>

<script>
// https://vueuse.org/guide/index.html
import { useMouse, usePreferredDark, useLocalStorage } from '@vueuse/core';
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  setup() {
    // tracks mouse position
    const { x, y } = useMouse();

    // is user prefers dark theme
    const isDark = usePreferredDark();

    // persist state in localStorage
    const store = useLocalStorage('my-storage', {
      name: 'Apple',
      color: 'red',
    });

    return { x, y, isDark, store };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
