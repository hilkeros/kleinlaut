<script>
  export let item;

  let detailOpen = false;

  function toggle() {
    detailOpen = !detailOpen;
  }
</script>

<div>
  <button on:click={toggle} class={detailOpen ? "selected" : ""}>
    <div>
      <span>{item.startTime}</span>
      <span class="artist-name">{item.name}</span>
    </div>
  </button>

  {#if detailOpen}
    <div class="video">
      <iframe
        width="560"
        height="315"
        src={item.videoUrl}
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      />
    </div>
  {/if}
</div>

<style>
  button {
    background: none;
    color: inherit;
    border: none;
    padding: 4px;
    font: inherit;
    cursor: pointer;
  }

  button:hover {
    background-color: black;
    color: white;
  }

  .selected {
    background-color: black;
    color: white;
  }

  .artist-name {
    margin-left: 12px;
  }
  .video {
    margin-top: 40px;
  }
</style>
