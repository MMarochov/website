<script lang="ts">
	import Counter from '../components/Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcomeFallback from '$lib/images/svelte-welcome.png';
</script>
<link
  href="https://fonts.googleapis.com/css2?family=Nixie+One&family=Open+Sans&family=Permanent+Marker&display=swap"
  rel="stylesheet"
/>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	
	<div id="name">
		<h2 class="intro">It's me,</h2>
      <h1 class="neon-text">
        <span>Melio</span>
      </h1>
	</div>

	<h2>
		updated site dropping soon :)
	</h2>

</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
		color: var(--color-bg-0);
	}

	.intro {
    font-family: "Permanent Marker", cursive;
    font-size: 2.2em;
    font-weight: normal;
  }

	h1 {
		width: 100%;
	}

h1 {font-family: "Lucida Sans Typewriter";
	    color: black;
    font-weight: 400;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    font-weight: bold;
    margin: 0px;
    font-size: 5.5rem;
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

</style>
