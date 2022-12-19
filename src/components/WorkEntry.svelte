<script>
  import SocialButton from "../components/SocialButton.svelte";

  export let image;
  export let title;
  export let description;
  export let github;
  export let webpage;
  let github_icon = "images/Github";
  let website_icon = "images/Website";
</script>

<article id="card">
  <div id="im-container">
    <img id="image" src={image} alt={title + " image"} />
  </div>
  <h3>{title}</h3>
  <p>{description}</p>
  {#if github}
  <SocialButton href={github} src={github_icon} alt="Link to github page"/>
  {/if}
  {#if webpage}
  <SocialButton href={webpage} src={website_icon} alt="Link to web page"/>
  {/if}
</article>

<style>
  #card {
    background: transparent;
    width: 300px;
    height: 390px;
    border-radius: 10px;
    box-shadow: 0 0 6px rgb(0 0 0 / 40%);
  }

  h3 {
    text-align: center;
    padding: 0px 40px 0px 40px;
    font-family: "Lucida Sans Typewriter";
  }

  #im-container {
    height: 150px;
    width: 90%;
    contain: content;
    margin: 15px;
    border-radius: 10px;
  }

  #image {
    width: 100%;
    border-radius: 10px;
  }
  p {
    padding: 0px 20px 0px 20px;
    font-size: 14px;
    text-align: left;
  }

  @media only screen and (max-width: 360px) {
    #card {
      width: 100%;
      display: table;
    }
  }
</style>
