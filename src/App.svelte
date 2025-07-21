<script>
  import { fade, fly } from "svelte/transition";
  import ImageExample from "./sections/ImageExample.svelte";
  import TitleSection from "./sections/TitleSection.svelte";
  import Window from "./lib/Window.svelte";
  import Digitization from "./sections/Digitization.svelte";

  let scroll;
  $: gradualRotation = Math.min(scroll ** 1.2, 90);
</script>

<svelte:window bind:scrollY={scroll} />
<h2 class="scroll-counter">{scroll}</h2>
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
      ></Window>
    </div>
    <div
      style:transform={`translate3d(0, ${scroll <= 1500 ? scroll : 0}px, 0)`}
    >
      {#if scroll <= 1400}
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

  <ImageExample />
</main>

<style>
  .scroll-counter {
    position: fixed;
    z-index: 10;
  }
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
