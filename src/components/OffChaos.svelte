<script>
  import ProgrammItem from "./ProgrammItem.svelte";
  import { rapido, aki } from "../data/offChaos";
  let selected = "";
</script>

<h2 class="date">IMMER WIEDER MAL</h2>
<ProgrammItem client:load item={rapido} bind:selected />

<h2 class="date">KONSTANT</h2>

<ProgrammItem client:load item={aki} bind:selected />
