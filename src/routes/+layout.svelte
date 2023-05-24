<script>
  import "../app.css";

  import { setContext } from 'svelte';
  import { writable } from 'svelte/store';
  import { player } from '../lib/player';

  /** @type {import('./$types').LayoutData} */
  // export let data;

  // Create a store and update it when necessary...
  const user = writable();
  $: user.set(player);

  // ...and add it to the context for child components to access
  setContext('user', user);
</script>

<style lang="postcss">
  :global(html) {
    background-color: theme(colors.gray.100);
  }
</style>

<svelte:head> <title>Energy Generator</title> </svelte:head>

<slot />