<!-- Name.svelte -->
<script>
  import Typed from "../components/Typed.svelte";
  import Mode from "../components/Mode.svelte";
  let name = "Mel";
</script>

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
  href="https://fonts.googleapis.com/css2?family=Nixie+One&family=Open+Sans&family=Permanent+Marker&display=swap"
  rel="stylesheet"
/>
<section id="name-container">
  <img src="images\mel_headshot.jpg" alt="{name}'s profile picture" />
  <section id="text-container">
    <p class="intro">
      <slot name="intro" />
    </p>
    <div id="name">
      <h1 class="neon-text">
        <slot name="name" />
      </h1>
      <Mode>Toggle</Mode>
    </div>
    <Typed
      strings={[
        "I like making things,",
        "and I think data science is pretty cool!",
        "oh also, the Earth is flat.",
      ]}
      loop="true"
      typeSpeed="9"
      startDelay="1200"
      backSpeed="9"
      backDelay="2600"
      cursorChar="|"
    >
      <h2 class="typing" />
    </Typed>
  </section>
</section>

<style>
  #name-container {
    display: inline-flex;
    align-items: left;
    max-width: 960px;
    margin: 10% 0 0 0;
  }

  #text-container {
    text-align: left;
    align-items: flex-start;
    font-family: "Lucida Sans Typewriter";
    line-height: 1;
    min-height: 175px;
    max-width: 960px;
    width: 100%;
    margin-left: 5%;
  }

  img {
    border-radius: 50%;
    width: 23%;
  }

  #name {
    display: inline-flex;
    align-items: flex-end;
  }

  .intro {
    font-family: "Permanent Marker", cursive;
    font-size: 2.2em;
    font-weight: normal;
    margin: 10px;
    margin-left: 4px;
  }

  h1 {
    color: black;
    font-weight: 400;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    font-weight: bold;
    margin: 0px;
    font-size: 5.5rem;
  }
  h2 {
    font-family: "Lucida Sans Typewriter";
    font-size: 1.5em;
  }

  :global(main.dark-mode) h1 {
    text-transform: uppercase;
    letter-spacing: 0.1em;
    font-weight: bold;
    margin: 0px;
    color: #fff;
    animation: pulsate 0.11s ease-in-out infinite alternate;
  }

  @keyframes pulsate {
    100% {
      text-shadow: 0 0 4px #fff, 0 0 11px #fff, 0 0 19px #fff, 0 0 40px #f585c8,
        0 0 80px #f585c8, 0 0 90px #f585c8, 0 0 100px #f585c8, 0 0 150px #f585c8;
    }

    0% {
      text-shadow: 0 0 4px #fff, 0 0 10px #fff, 0 0 18px #fff, 0 0 38px #f585c8,
        0 0 73px #f585c8, 0 0 80px #f585c8, 0 0 94px #f585c8, 0 0 140px #f585c8;
    }
  }

  @media only screen and (max-width: 1100px) {
    #name-container {
      display: block;
      text-align: left;
    }

    #text-container {
      display: flex;
      flex-wrap: wrap;
      flex-direction: column;
      margin-left: auto;
      min-height: 210px;
    }
  }

  @media only screen and (max-width: 670px) {
    #name-container {
      display: flex;
      flex-direction: column;
      align-items: center;
  }
    #text-container {
      min-height: 180px;
      align-items: center;
    }
    h1 {
      font-size: 3em;
      max-width: 270px;
    }
    .intro {
      font-size: 1.5em;
    }
    h2 {
      font-size: 1.1em;
      max-width: 270px;
    }
  }
</style>
