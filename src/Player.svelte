<script>
  export let showFloat;
  let videoCont;
  let Player;

  // handle clicking X to remove floating player
  const hideSmallPlayer = () => {
    videoCont.classList.remove("float");
    Player.classList.remove("sm-player");
  };
</script>

<div
  id="video-cont"
  class="video-cont"
  class:float={showFloat}
  bind:this={videoCont}
>
  {#if showFloat}
    <div id="close-icon" on:click={hideSmallPlayer}>X</div>
  {/if}

  // video from :
  https://www.istockphoto.com/video/time-lapse-sunrise-over-mountain-with-mist-and-fog-cloud-gm1125217870-295706751?utm_source=pixabay&utm_medium=affiliate&utm_campaign=SRP_video_noresults&referrer_url=https%253A//pixabay.com/videos/fog-mountains-road-foggy-dramatic-53358/&utm_term=

  <video
    class="vid-player"
    controls
    class:sm-player={showFloat}
    bind:this={Player}
  >
    <track kind="captions" />
    <source
      src="https://media.istockphoto.com/videos/time-lapse-sunrise-over-mountain-with-mist-and-fog-cloud-video-id1125217870"
      type="video/webm"
    />
    <source
      src="https://media.istockphoto.com/videos/time-lapse-sunrise-over-mountain-with-mist-and-fog-cloud-video-id1125217870"
      type="video/mp4"
    />
    Oops, looks like your browser doesn't support embedded videos.
  </video>
</div>

<style>
  .video-cont {
    max-width: 90%;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    z-index: 10;
    padding-left: 5rem;
    padding-right: 5rem;
  }

  .vid-player {
    width: 100%;
    height: 100%;
    border-radius: 3%;
  }

  #close-icon {
    display: block;
    position: absolute;
    font-size: 1rem;
    color: black;
    font-weight: 800;
    top: 1%;
    left: 3%;
    cursor: pointer;
  }

  #close-icon:active {
    color: white;
  }

  /* small video player when scrolling */
  @keyframes fade {
    100% {
      opacity: 1;
    }
  }

  @keyframes enterR {
    0% {
      left: -40%;
    }
  }

  .sm-player {
    width: 270px;
    height: 160px;
  }

  .float {
    animation: enterR 0.5s ease-in-out;
    width: 260px;
    height: 200px;
    box-shadow: 1 0 7px darkgray;
    background-color: darkgrey;
    position: fixed;
    bottom: 1%;
    left: 1%;
  }
</style>
