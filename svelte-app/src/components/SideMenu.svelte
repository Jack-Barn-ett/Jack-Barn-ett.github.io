<script>
  import { slide } from 'svelte/transition';
  let open = false;
  let projects = ['Project 1', 'Project 2', 'Project 3'];
</script>

<button on:click={() => open = !open}>
  {open ? 'Hide' : 'Show'} Projects
</button>

{#if open}
  <ul transition:slide>
    {#each projects as project (project)}
      <li>{project}</li>
    {/each}
  </ul>
{/if}

<style>
  ul {
    list-style-type: none;
    padding-left: 0;
    margin-top: 15px;
  }
  button {
    margin-top: 15px;
  }
</style>
