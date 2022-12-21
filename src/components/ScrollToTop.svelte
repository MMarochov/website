<!-- ScrollToTop.svelte -->
<script>
  let hidden = true;
  let showOnPx;

  calcShowOnPx();
  window.addEventListener("resize", calcShowOnPx);

  function calcShowOnPx() {
    if (window.matchMedia("(max-width: 810px)").matches) {
      showOnPx = 3400;
    } else {
      showOnPx = 150;
    }
  }

  function goTop() {
    document.body.scrollIntoView({
      behavior: "smooth",
    });
  }

  function scrollContainer() {
    return document.documentElement || document.body;
  }

  function handleOnScroll() {
    if (!scrollContainer()) {
      return;
    }

    if (scrollContainer().scrollTop > showOnPx) {
      hidden = false;
    } else {
      hidden = true;
    }
  }
</script>

<svelte:window on:scroll={handleOnScroll} />

<div class="back-to-top" on:click={goTop} class:hidden>
  <span class="material-symbols-outlined"> arrow_circle_up</span>
</div>

<style>
  span {
    font-size: 2.5rem;
  }

  .back-to-top {
    transition: opacity 0.5s, visibility 0.5s;
    position: fixed;
    right: 20px;
    user-select: none;
    bottom: 20px;
    color: #000;
  }

  .back-to-top.hidden {
    opacity: 0;
    visibility: hidden;
  }

  :global(main.dark-mode) .back-to-top {
    color: #d7e3f5;
  }

  @media only screen and (max-width: 670px) {
    span {
      font-size: 2rem;
    }
    .back-to-top {
      bottom: 10px;
      width: 90%;
      position: fixed;
    }
  }
</style>
