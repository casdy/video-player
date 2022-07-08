<script>
 
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
