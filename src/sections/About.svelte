<!-- About.svelte -->

<p>
  <slot />
</p>

<style>
  p {
    display: inline-block;
    text-align: left;
    font-size: 1.15em;
    font-weight: 490;
    margin: 0px;
  }

  @media only screen and (max-width: 376px) {
    p {
      font-size: 1em;
    }
  }
</style>
