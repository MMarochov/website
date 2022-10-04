<script>
  import Name from "./components/Name.svelte";
  import About from "./sections/About.svelte";
  import Work from "./sections/Work.svelte";
</script>

<main>
  <section id="landing-page">
    <Name />
    <About>
      I'm Mel Marochov, a trainee geospatial data scientist and web developer at
      Ordnance Survey. In my spare time I love skateboarding, wild swimming, and
      climbing! At work I've been learning some pretty cool things from some
      pretty cool people, from a wee bit of Python to a fair amount of
      development... but mainly just an outrageous number of keyboard shortcuts.
    </About>
  </section>
  <Work />
</main>

<style>
  #landing-page {
    height: 100vh;
  }
  :global(body) {
    padding: 20px;
  }
  :global(body),
  :global(html) {
    margin: 0;
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
</style>
