<!-- NavButton.svelte -->
<script>
  // Props
  export let href;

  // Init
  function scrollIntoView({ currentTarget }) {
    const el = document.querySelector(currentTarget.getAttribute("href"));
    if (!el) return;
    el.scrollIntoView({
      behavior: "smooth",
    });
  }
</script>

<a {href} on:click|preventDefault={scrollIntoView}>
  <slot />
</a>

<style>
  a {
    padding: 20px 40px 12px 0px;
    width: fit-content;
    border-radius: 3px;
    color: black;
    font-family: "Permanent Marker", cursive;
    font-size: 1.5rem;
  }

  a:hover {
    text-decoration: underline;
    text-decoration-color: rgb(149, 116, 252, 0.5);
    text-decoration-thickness: 5px;
  }

  :global(main.dark-mode) a {
    color: #d7e3f5;
  }

  :global(main.dark-mode) a:hover {
    text-decoration: underline;
    text-decoration-color: #d7e3f5;
    text-decoration-thickness: 5px;
  }
</style>
