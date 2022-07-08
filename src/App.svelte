<script>
  // video from : https://www.istockphoto.com/video/time-lapse-sunrise-over-mountain-with-mist-and-fog-cloud-gm1125217870-295706751?utm_source=pixabay&utm_medium=affiliate&utm_campaign=SRP_video_noresults&referrer_url=https%253A//pixabay.com/videos/fog-mountains-road-foggy-dramatic-53358/&utm_term=

  import Blog from "./Blog.svelte";
  import Player from "./Player.svelte";

  let scroll;
  // $: console.log(y)
  $: scroll > 850 ? (showFloat = true) : (showFloat = false);

  let showFloat = false;
</script>

<svelte:window bind:scrollY={scroll} />

<header>
  <div class="heads">
    <Player {showFloat} />
  </div>
</header>

<main>
  <Blog />
</main>

<style>
  .heads {
    position: relative;
    justify-content: center;
    justify-self: center;
    padding-left: 10rem;
    padding-right: 10rem;
  }
  header {
    width: 100%;
    display: relative;
    padding: -10rem -10rem -10rem;
  }

  main {
    width: 100vw;

    height: 300vh;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
  }
</style>
