<h1 align='center'>⚡️ VueUse Vite Starter</h1>

<p align='center'>
<img src='./src/logo.svg' height='120'/>
</p>


Starter for [Vite](https://github.com/vuejs/vite) + [VueUse](https://github.com/vueuse/vueuse) + [TypeScript](https://www.typescriptlang.org/)

🌐 [Live Demo](https://vueuse-vite-starter.netlify.app/)

📦 [Webpack Example](https://github.com/vueuse/vueuse-vue3-example)

## Debug

> [plugin:vite:vue] [@vue/compiler-sfc] `<script setup>` cannot contain ES module exports.

`<script setup lang="ts">` setup: ()

```js
<script setup lang="ts">
import { useMouse } from '@vueuse/core'
const { x, y } = useMouse()
</script>
```

```js
<script lang="ts">
import { defineComponent } from 'vue';
import { useMouse } from '@vueuse/core';
export default defineComponent({
  setup: () => {
    const { x, y } = useMouse();
    return { x, y };
  },
});
</script>
```

## Installation

1. Clone this repository
2. `yarn`
3. `yarn dev`
4. open http://localhost:3000 in your browser

## More Example

Enjoy using Vite and VueUse? Check out the real world template [Vitesse](https://github.com/antfu/vitesse)!

## License

[MIT](http://opensource.org/licenses/MIT)
