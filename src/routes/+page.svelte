<script lang="ts">
  import CausesCard from '$lib/cards/CausesCard.svelte';
  import ConsequencesCard from '$lib/cards/ConsequencesCard.svelte';
  import CreditsCard from '$lib/cards/CreditsCard.svelte';
  import SolutionsCard from '$lib/cards/SolutionsCard.svelte';
  import SpaceCard from '$lib/cards/SpaceCard.svelte';
  import About from '$lib/deepdives/About.svelte';
  import Consequences from '$lib/deepdives/Consequences.svelte';
  import Credits from '$lib/deepdives/Credits.svelte';
  import Solutions from '$lib/deepdives/Solutions.svelte';
  import Research from '$lib/deepdives/Research.svelte';
  import { cubicInOut } from 'svelte/easing';
  import { fly } from 'svelte/transition';

  let isDeepDiveCausesOpen = false;
  let isDeepDiveCreditsOpen = false;
  let isDeepDiveConsequencesOpen = false;
  let isDeepDiveResearchOpen = false;
  let isDeepDiveSolutionsOpen = false;
  let showSlogan = false;

  $: isAnyDeepDiveOpen = !isDeepDiveCausesOpen && !isDeepDiveCreditsOpen && !isDeepDiveConsequencesOpen && !isDeepDiveResearchOpen && !isDeepDiveSolutionsOpen;

  function handleTypewriterFinish() {
    setTimeout(() => {
      showSlogan = true;
    }, 500); // Wait 500ms after typing completes, then show slogan
  }
</script>

{#if isAnyDeepDiveOpen}
  <div transition:fly={{ duration: 1000, easing: cubicInOut, x: '-90dvw' }} class="will-change-transform">
    <!--
    <div class="color-transition fixed top-0 z-50 flex h-screen w-full items-center justify-center px-4 py-2" bind:this={notification}>
      <div class="w-14 flex-shrink" />
      <div class="text-center mt-6 w-full relative">
        <Typewriter 
          on:done={handleTypewriterFinish}
          interval={100}
          delay={1000}
          cursor={true}
        >
          <h2 class="text-8xl font-bold md:text-9xl space-text">
            Water Scarcity.
          </h2>
        </Typewriter>
      </div>
    </div>
    -->
    <div class="mx-auto grid h-full max-w-[980px] auto-rows-[18rem] grid-cols-1 justify-center gap-2 py-4 md:grid-cols-[21rem_11rem_21rem] md:gap-5">
      <CausesCard bind:isDeepDiveOpen={isDeepDiveCausesOpen} />
      <CreditsCard bind:isDeepDiveOpen={isDeepDiveCreditsOpen} />
      <SpaceCard bind:isDeepDiveOpen={isDeepDiveResearchOpen} />
      <ConsequencesCard bind:isDeepDiveOpen={isDeepDiveConsequencesOpen} />
      <SolutionsCard bind:isDeepDiveOpen={isDeepDiveSolutionsOpen} />
    </div>
  </div>
{/if}

<About bind:isDeepDiveCausesOpen />

<Credits bind:isDeepDiveCreditsOpen />

<Consequences bind:isDeepDiveConsequencesOpen />

<Research bind:isDeepDiveResearchOpen />

<Solutions bind:isDeepDiveSolutionsOpen />
<!--
<style>
  :root {
    --cursor-color: #ffffff;
    --cursor-width: 3px;
  }
  .color-transition {
    animation: colorTransition 3s ease-in-out forwards, slideUp 1s ease-in-out 6s forwards;
  }

  .space-text {
    color: transparent !important;
    background: url('https://www.urbanexile.net/wordpress/wp-content/uploads/2015/03/Starfield_Instancing_white_uniform.png');
    background-size: 500px 500px;
    background-position: center;
    background-repeat: repeat;
    -webkit-background-clip: text;
    background-clip: text;
  }

  @keyframes colorTransition {
    0% {
      background-color: #3a6fe4; /* blue */
    }
    50% {
      background-color: #2563eb; /* blue */
    }
    100% {
      background-color: #000000; /* black */
    }
  }

  @keyframes slideUp {
    0% {
      transform: translateY(0);
    }
    100% {
      transform: translateY(-100vh);
    }
  }
</style>
-->