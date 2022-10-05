<!-- About.svelte -->

<p>
  <slot />
</p>

<style>
  p {
    display: inline-block;
    text-align: left;
    font-size: 1.1em;
  }

  @media only screen and (max-width: 376px) {
    p {
      font-size: 1em;
    }
  }
</style>
