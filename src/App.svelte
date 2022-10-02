<script>
  import Work from "./sections/Work.svelte";
</script>

<main>
  <Work />
</main>

<style>
  :global(body) {
    padding: 20px;
  }
  :global(body),
  :global(html) {
    margin: 0;
    width: 100%;
    height: fit-content;
  }

  :global(html) {
    background: radial-gradient(
        circle at 50% 20%,
        rgba(255, 0, 0, 0.25),
        rgba(255, 0, 0, 0) 70.71%
      ),
      radial-gradient(
        circle at 6.7% 85%,
        rgba(149, 116, 252, 0.7),
        rgba(0, 0, 255, 0) 70.71%
      ),
      radial-gradient(
        circle at 95% 45%,
        rgba(116, 252, 227, 0.5),
        rgba(0, 255, 0, 0) 70.71%
      ),
      radial-gradient(
        circle at 17% 100%,
        rgba(255, 0, 110, 0.4),
        rgba(0, 0, 255, 0) 70.71%
      ),
      white;
  }

  main {
    text-align: center;
    width: 100%;
    max-width: 960px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
