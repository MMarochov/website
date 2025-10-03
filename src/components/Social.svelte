<!-- Social.svelte -->
<script>
  export let name;
  export let href;
  export let icon;
</script>

<p class="hover-1">
  <i class={icon}></i>
  <a {href} target="_blank">{name}</a>
</p>

<style>

  .hover-1 {
  background: linear-gradient(
    to right top,
    #4286ae,
    #4c87b0,
    #4b9fc1,
    #51b7cf,
    #62cfd8,
    #7ce6de
  );
  background-size: 0 100%;
  background-repeat: no-repeat;
  transition: 0.4s;
}

.hover-1:hover {
  background-size: 100% 100%;
  color: #fff;
}

a {
  color: inherit;
}
  p {
    margin: 1em 0 0 0;
    padding: 3px 10px;
    display: flex;
    align-items: center;
    border-radius: 10px;
  }

  i {
    font-size: larger;
  }

  a {
    margin-left: 5px;
  }
</style>
