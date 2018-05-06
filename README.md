# svelte-transitions-slide

Slide transition plugin for [Svelte](https://svelte.technology). [Demo](https://svelte.technology/repl?version=2.5.0&gist=b447904fdd05737538c24268cca144cc)

![slide-hello](https://cloud.githubusercontent.com/assets/1162160/25782611/50b10200-331c-11e7-9cd9-9ce8cbaf3f33.gif)

Note that this transition will behave oddly with `display: inline` elements.

## Usage

Recommended usage is via [svelte-transitions](https://github.com/sveltejs/svelte-transitions), but you can use this module directly if you prefer. Note that it assumes an ES module or CommonJS environment.

Install with npm or yarn:

```bash
npm install --save svelte-transitions-slide
```

Then add the plugin to your Svelte component's exported definition:

```html
<label>
  <input type='checkbox' bind:checked='visible'> visible
</label>

{#if visible}
  <!-- use `in`, `out`, or `transition` (bidirectional) -->
  <div transition:slide>hello!</div>
{/if}

<script>
  import slide from 'svelte-transitions-slide';

  export default {
    transitions: { slide }
  };
</script>
```


## Parameters

You can specify `delay` and `duration` parameters, which default to `0` and `400` respectively, and a custom `easing` function (which should live on your `helpers`):

```html
<div in:fade='{duration: 1000, easing: quintInOut}'>
  slides in slowly
</div>

<script>
  import slide from 'svelte-transitions-slide';
  import { quintInOut } from 'eases-jsnext';

  export default {
    helpers: { quintInOut },
    transitions: { slide }
  };
</script>
```


## License

[MIT](LICENSE)
