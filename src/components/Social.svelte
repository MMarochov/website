<!-- Social.svelte -->
<script>
  // Imports
  import SocialButton from "../components/SocialButton.svelte";
</script>

<div>
  <SocialButton
    href="https://uk.linkedin.com/in/melanie-marochov-a41385172"
    src="images/LinkedIn"
    alt="LinkedIn"
  />
  <SocialButton
    href="https://github.com/MMarochov"
    src="images/Github"
    alt="Github"
  />
</div>

<style>
  div {
    display: flex;
    height: 30px;
  }

  @media only screen and (max-width: 670px) {
    div {
      padding-top: 20px;
    }
  }
</style>
