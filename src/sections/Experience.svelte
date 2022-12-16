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
  }

  p {
    margin: 0;
  }

  .timeline li {
    position: relative;
    display: flex;
    justify-content: space-around;
  }

  .timeline .panel {
    width: 70%;
    overflow: hidden;
    position: relative;
    border-radius: 10px;
    box-shadow: 0 0 6px rgba(0, 0, 0, 0.148);
  }

  .timeline .description {
    padding: 1rem;
    border-radius: 10px;
    margin: 0;
    text-align: left;
  }

  .timeline summary {
    user-select: none;
    cursor: pointer;
    padding: 1rem;
    display: flex;
  }
  
  .timeline summary:hover {
    background: rgba(0, 0, 0, 0.023);
    border-radius: 10px;
  }

  .timeline:before {
    top: 0;
    bottom: 0;
    left: 22%;
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
    left: 22%;
    top: 30px;
    background: #000;
    position: absolute;
    box-shadow: 1px 1px 6px #0000003a, -1px -1px 6px #0000001f;
  }
</style>
