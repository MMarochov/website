<!-- ScrollArrow.svelte -->
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
  <p>scroll</p>
  <span id="arrow" class="material-symbols-outlined"> south </span>
</a>

<style>
  p {
    font-family: "Permanent Marker", cursive;
    font-size: 1.2rem;
    margin-bottom: 5px;
    color: black;
    text-decoration: none;
  }
  
  :global(main.dark-mode) p {
    color: #d7e3f5;
  }

  a {
    display: block;
    align-self: center;
    margin: 0px 0px 30px 0px;
  }

  a:hover {
    text-decoration: none;
  }

  #arrow {
    animation: scroll 0.5s ease-in alternate infinite;
    font-size: 30px;
    font-weight: 500;
    color: black;
  }

  :global(main.dark-mode) #arrow {
    color: rgb(214, 226, 245);
  }

  @keyframes scroll {
    0% {
      transform: translateY(0);
    }
    100% {
      transform: translateY(18px);
    }
  }
</style>
