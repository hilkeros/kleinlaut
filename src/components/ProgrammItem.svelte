<script>
  export let item;
  export let selected;

  function toggle() {
    if (selected === item.name) {
      selected = "";
    } else {
      selected = item.name;
    }
  }
</script>

<div>
  <button on:click={toggle} class={selected === item.name ? "selected" : ""}>
    <div>
      {#if item.startTime}
        <span>{item.startTime}</span>
      {/if}
      <span class="artist-name">{item.name}</span>
    </div>
  </button>

  {#if selected === item.name}
    {#if item.description}
      <div class="description">{item.description}</div>
    {/if}
    {#if item.videoUrl}
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
    {#if item.imgUrl}
      <div class="image"><img src={item.imgUrl} alt={item.name} /></div>
    {/if}
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

  .description {
    margin-top: 40px;
    margin-bottom: 20px;
  }
  .video {
    margin-top: 40px;
    margin-bottom: 20px;
  }

  .image {
    text-align: center;
  }
  .image img {
    width: 360px;
    margin: 20px;
  }

  @media screen and (max-width: 767px) {
    iframe {
      max-width: 100% !important;
      width: auto !important;
      height: auto !important;
    }

    .image img {
      width: 80%;
      margin: 20px;
    }
  }
</style>
