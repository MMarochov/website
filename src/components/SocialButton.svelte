<!-- SocialButton.svelte -->
<script>
  // Props
  export let href;
  export let src;
  export let alt;
  import { darkMode } from "../stores/darkMode.js";
  let dark = "_darkmode.svg";
  let light = "_lightmode.svg";
</script>

<a {href} target="_blank" rel="noreferrer"
  >{#if $darkMode}<img src="{src}{dark}" {alt} />{:else}<img
      src="{src}{light}"
      {alt}
    />{/if}<slot /></a
>

<style>
  a {
    padding-right: 15px;
  }

  img {
    height: 27px;
  }

  img:hover {
    height: 30px;
  }
</style>
