<!-- ExperienceEntry.svelte -->
<script>
  // Imports
  import { slide } from "svelte/transition";

  // Props
  export let open;
  export let org;
  export let role;
  export let months;
  export let years;
  export let description;
  let isOpen = false;
  const toggle = () => (isOpen = !isOpen);
  if (open) isOpen = true;
</script>

<div id="container">
  <div>
    <p>{months}</p>
    <p id="years">{years}</p>
  </div>

  <button on:click={toggle} expanded={isOpen}>
    <span class="material-symbols-outlined"> horizontal_rule </span>
    <span id="rotate" class="material-symbols-outlined">play_arrow</span>
    {role} @ {org}
  </button>
</div>
{#if isOpen}
  <div id="description" transition:slide={{ duration: 300 }}>
    {description}
  </div>
{/if}

<style>
  #container {
    display: flex;
    align-items: center;
    margin: 25px;
    font-family: "Lucida Sans Typewriter";
  }

  p {
    width: 100px;
    font-size: 13px;
    margin: 5px;
    font-family: "Lucida Sans Typewriter";
  }

  #years {
    font-weight: bold;
  }
  button {
    display: contents;
    border: none;
    background: none;
    color: inherit;
    font-size: 20px;
    cursor: pointer;
  }

  #description {
    text-align: left;
    padding: 15px;
    margin-left: 190px;
    width: 70%;
    border-radius: 10px;
    box-shadow: 0 0 6px rgb(0 0 0 / 40%);
  }

  #rotate {
    transition: transform 0.2s ease-in;
    padding: 0px;
  }

  [expanded="true"] #rotate {
    transform: rotate(0.25turn);
  }
</style>
