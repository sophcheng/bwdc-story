<script>
  import { fade, fly } from "svelte/transition";
  import TitleSection from "./sections/TitleSection.svelte";
  import Window from "./lib/Window.svelte";
  import Digitization from "./sections/Digitization.svelte";
  import Postcard from "./lib/Postcard.svelte";

  let scroll;

  $: gradualRotation = Math.min(scroll ** 1.2, 90);
</script>

<svelte:window bind:scrollY={scroll} />
<!-- <h2 class="scroll-counter">{scroll}</h2> -->
<main>
  <!-- Title Card -->
  <div class="container">
    <div
      class="window-container"
      style:transform={`rotate(${gradualRotation}deg) translate3d(${scroll}px, ${scroll}px, 0)`}
    >
      <Window
        title={"Stand Clear of the Closing Gap"}
        subtitle={"by Sophie Cheng"}
        caption={"(how physical + digital connection shape the road to employment + diversity)"}
        {scroll}
      ></Window>
    </div>
    <div
      style:transform={`translate3d(0, ${scroll <= 4700 ? scroll : 0}px, 0)`}
    >
      {#if scroll <= 4600}
        <div in:fly={{ y: 200, duration: 500 }} out:fade>
          <TitleSection />
        </div>
      {/if}
    </div>
  </div>
  {#if scroll >= 500}
    <div in:fly={{ y: 200, duration: 500 }} out:fade>
      <Digitization />
    </div>
  {/if}
  {#if scroll >= 4400 && scroll <= 5500}
    <div in:fly={{ y: 200, duration: 500 }} out:fade>
      <Postcard {scroll}></Postcard>
    </div>
  {/if}
</main>

<style>
  /* .scroll-counter {
    position: fixed;
    z-index: 10;
  } */
  .window-container {
    position: absolute;
    top: -20px;
    right: 100px;
    z-index: 2;
  }
  .container {
    position: relative;
  }
</style>
