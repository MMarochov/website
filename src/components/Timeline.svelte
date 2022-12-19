<!-- ExperienceEntry.svelte -->
<script>
  // Imports
  import { slide } from "svelte/transition";

  // Props
  export let open;
  export let org;
  export let role;
  export let months;
  export let years;
  export let description;

  let isOpen = false;
  const toggle = () => (isOpen = !isOpen);
  if (open) isOpen = true;
</script>

<article id="timeline">
  <section id="timeline-entry">
    <div id="date">
      <p>{months}</p>
      <p>{years}</p>
    </div>
    <summary id="panel" on:click={toggle}>
      <button>
        {role} @ {org}
      </button>
      {#if isOpen}
        <p id="description" transition:slide={{ duration: 300 }}>
          {description}
        </p>
      {/if}
    </summary>
  </section>
</article>

<style>
  #timeline {
    width: 100%;
    max-width: 960px;
    display: flex;
  }

  #timeline-entry {
    position: relative;
    width: 100%;
    margin: 0px;
    padding: 0.6rem 0 0.6rem;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  #date {
    width: 15%;
    padding-top: 0.3rem;
    font-family: "Lucida Sans Typewriter";
    font-size: 0.8rem;
    font-weight: bold;
  }

  p {
    margin: 0;
  }

  #panel {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    width: 70%;
    overflow: hidden;
    position: relative;
    border-radius: 10px;
    box-shadow: 0 0 6px rgba(0, 0, 0, 0.148);
    padding: 1rem;
    cursor: pointer;
  }

  #panel:hover {
    background: rgba(0, 0, 0, 0.023);
    border-radius: 10px;
  }

  button {
    display: contents;
    border: none;
    background: none;
    color: inherit;
    cursor: pointer;
    font-family: "Lucida Sans Typewriter";
  }

  #description {
    text-align: left;
    padding-top: 15px;
  }

  #timeline-entry:before {
    top: 0;
    bottom: 0;
    left: 20%;
    position: absolute;
    content: "";
    width: 0.1rem;
    background: #000;
    box-shadow: 1px 1px 6px #0000003a, -1px -1px 6px #0000001f;
  }

  #timeline-entry:after {
    content: "";
    height: 0.1rem;
    width: 0.8rem;
    left: 20%;
    background: #000;
    position: absolute;
    box-shadow: 1px 1px 6px #0000003a, -1px -1px 6px #0000001f;
  }

  @media only screen and (max-width: 1050px) {
    #timeline {
      max-width: 80%;
    }

    #timeline-entry {
      justify-content: center;
      align-items: center;
      display: block;
      text-align: left;
    }

    #timeline-entry:before {
      display: none;
    }

    #timeline-entry:after {
      display: none;
    }

    #panel {
      box-shadow: 0 0 6px rgba(0, 0, 0, 0.148);
      width: 100%;
      align-items: flex-end;
    }

    #date {
      position: absolute;
      padding-left: 1rem;
      width: 40%;
    }

    #description {
      padding-top: 25px;
    }
  }

  @media only screen and (max-width: 810px) {
    #timeline {
      padding: 0.6rem 0 0.6rem;
    }

    #timeline-entry {
      display: flex;
      flex-direction: column;
      border-radius: 10px;
      box-shadow: 0 0 6px rgba(0, 0, 0, 0.148);
      justify-content: left;
      padding: 0.6rem;
      background: rgba(0, 0, 0, 0.023);
    }

    #date {
      position: unset;
      width: 100%;
      display: flex;
      justify-content: space-between;
      flex-direction: row;
      padding: 0;
    }

    #panel {
      box-shadow: none;
      padding: 0;
      background: 0;
      align-items: flex-start;
    }
  }
</style>
