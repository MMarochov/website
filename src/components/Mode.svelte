<!-- Mode.svelte -->
<script>
  import { darkMode } from "../stores/darkMode.js";

  function toggle() {
    $darkMode = !$darkMode;
  }
</script>

<button on:click={toggle}>
  {#if $darkMode}
    <img src="images/sun.svg" alt="sun for toggle light mode" />
  {:else}
    <img src="images/moon.svg" alt="moon for toggle light mode" />
  {/if}
</button>

<style>
  button {
    background-color: transparent;
    border: none;
    padding: none;
    border-radius: 4px;
    text-transform: uppercase;
    cursor: pointer;
  }
  :global(main.dark-mode) button {
    background-color: transparent;
  }
</style>
