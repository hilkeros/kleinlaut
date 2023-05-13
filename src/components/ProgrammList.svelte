<script>
  import ProgrammItem from "./ProgrammItem.svelte";
  export let bandsFriday;
  export let bandsSaturday;
  let selected = "";
</script>

<h2 class="date">FREITAG 28.JULI</h2>
{#each bandsFriday as item}
  <ProgrammItem client:load {item} bind:selected />
{/each}
<h2 class="date">SAMSTAG 29.JULI</h2>
{#each bandsSaturday as item}
  <ProgrammItem client:load {item} bind:selected />
{/each}
