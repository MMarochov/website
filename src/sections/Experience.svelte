<!-- Experience.svelte -->
<script>
  import { slide } from "svelte/transition";

  let isOpen = false;
  const toggle = () => (isOpen = !isOpen);
</script>

<div class="wrapper">
  <ul class="timeline">
    <li>
      <p class="time">
        <slot name="months" />
        <slot name="year" />
      </p>
      <details class="panel">
        <summary on:click={toggle}>
          <p><slot name="role" /> @ <slot name="org" /></p>
        </summary>

        {#if isOpen}
          <p class="description" transition:slide={{ duration: 300 }}>
            <slot name="description" />
          </p>
        {/if}
      </details>
    </li>
  </ul>
</div>

<style>
  .wrapper {
    width: 100%;
    max-width: 960px;
    display: flex;
    justify-content: center;
  }

  .timeline {
    list-style: none;
    padding: 10px 0 10px;
    position: relative;
    width: 100%;
    margin: 0px;
  }

  .time {
    position: relative;
    display: flex;
    flex-direction: column;
    margin: 0;
    width: 15%;
    padding-top: 0.3rem;
    font-family: "Lucida Sans Typewriter";
    font-size: .8rem;
    font-weight: bold;
  }

  p {
    margin: 0;
  }

  .timeline li {
    position: relative;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .timeline .panel {
    width: 70%;
    overflow: hidden;
    position: relative;
    border-radius: 10px;
    box-shadow: 0 0 6px rgba(0, 0, 0, 0.148);padding: 1rem;
  }

  .timeline .description {
    width: none;
    padding-top: 15px;
    border-radius: 10px;
    text-align: left;
  }

  .timeline summary {
    user-select: none;
    cursor: pointer;
    /* padding: 1rem; */
    display: flex;
    font-family: "Lucida Sans Typewriter";
  }

  .timeline .panel:hover {
    background: rgba(0, 0, 0, 0.023);
    border-radius: 10px;
  }

  .timeline:before {
    top: 0;
    bottom: 0;
    left: 20%;
    position: absolute;
    content: "";
    width: 0.1rem;
    background: #000;
    box-shadow: 1px 1px 6px #0000003a, -1px -1px 6px #0000001f;
  }

  .timeline li:before {
    content: "";
    height: 0.1rem;
    width: 0.8rem;
    left: 20%;
    top: 28px;
    background: #000;
    position: absolute;
    box-shadow: 1px 1px 6px #0000003a, -1px -1px 6px #0000001f;
  }

  @media only screen and (max-width: 1050px) {
    .wrapper {
      /* width: 100%; */
      max-width: 80%;
    }
    .timeline:before {
      display: none;
    }
    .timeline li:before {
      display: none;
    }

    .timeline li {
      justify-content: center;
      align-items: center;
      display: block;
      text-align: left;
    }
    .timeline summary {
      flex-direction: row-reverse;
    }

    .timeline .panel {
      box-shadow: 0 0 6px rgba(0, 0, 0, 0.148);
      width: 100%;
    }

    .time {
      position: absolute;
      padding-left: 1rem;
      width: 40%;
    }

    .timeline .description {
    padding-top: 25px;
  }

  @media only screen and (max-width: 810px) {
    .timeline li {
      display: flex;
      flex-direction: column;
      border-radius: 10px;
      box-shadow: 0 0 6px rgba(0, 0, 0, 0.148);
      justify-content: left;
      padding: .6rem;
      /* background: rgba(0, 0, 0, 0.023); */
    }
    .time {
      position: unset;
      width: 100%;
      flex-direction: row;
      justify-content: space-between;
      padding: 0;
    }
    .timeline .panel {
      box-shadow: none;
      padding: 0;
      background: 0;
    }
    .timeline summary {
      flex-direction: row;
    }
  }}
</style>
