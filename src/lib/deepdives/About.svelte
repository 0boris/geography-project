<script lang="ts">
  import videoPosterImage from '$assets/images/jpg/wonderfultools_thumbnail.jpg';
  import HomeImage from '$assets/images/png/home.png';
  import ScarcityGraph from '$assets/images/webp/ScarcityGraph.webp';
  import SheikhImage from '$assets/images/webp/Sheikh.webp';
  import AquiferImage from '$assets/images/webp/Aquifer.webp';
  import AfricaImage from '$assets/images/webp/AfricaWater.webp';
  import GlobalGraph from '$assets/images/webp/GlobalGraph.webp';
  import WaterStressImage from '$assets/images/webp/WaterStress.webp';
  import Image from '$lib/components/image.svelte';
  import VisionButtons from '$lib/components/visionOS/visionButtons.svelte';
  import VisionWindow from '$lib/components/visionOS/visionWindow.svelte';
  import Deepdive from '$lib/layout/Deepdive.svelte';
  import type { Picture } from '$lib/types';

  import { cubicInOut } from 'svelte/easing';
  import { slide } from 'svelte/transition';

  const HomeImg = HomeImage as unknown as Picture;
  const ScarcityGraphImg = ScarcityGraph as unknown as Picture;
  const SheikhImg = SheikhImage as unknown as Picture;
  const AquiferImg = AquiferImage as unknown as Picture;
  const AfricaGraphImg = AfricaImage as unknown as Picture;
  const GlobalImg = GlobalGraph as unknown as Picture;
  const WaterStressImg = WaterStressImage as unknown as Picture;

  export let isDeepDiveCausesOpen: boolean;

  let yorkshireOpen = true;
  let arabiaOpen = false; // REMEMBER TO CHANGE NEGA
  let africaOpen = false;
  let globalOpen = false;

  let zoomGraph = false;
  let zoomGraph2 = false;
  let zoomGraph3 = false;

  let form: HTMLFormElement;
  let submitButton: HTMLButtonElement;

  function open(card: string) {
    yorkshireOpen = false;
    arabiaOpen = false;
    africaOpen = false;
    globalOpen = false;
    switch (card) {
      case 'yorkshire':
        yorkshireOpen = true;
        break;
      case 'arabia':
        arabiaOpen = true;
        break;
      case 'africa':
        africaOpen = true;
        break;
      case 'global':
        globalOpen = true;
        break;
    }
  }

  function zoom() {
    zoomGraph = true;

    setTimeout(() => {
      zoomGraph = false;
    }, 2000);
  }

  function zoom2() {
    zoomGraph2 = true;

    setTimeout(() => {
      zoomGraph2 = false;
    }, 2000);
  }

  function zoom3() {
    zoomGraph3 = true;

    setTimeout(() => {
      zoomGraph3 = false;
    }, 2000);
  }
</script>

<Deepdive bind:isDeepDiveOpen={isDeepDiveCausesOpen} class="relative">
  <Image class="pointer-events-none fixed inset-0 h-full w-full select-none bg-fixed object-cover object-center blur-sm" src={HomeImg} alt="Star Trails" />
  <VisionWindow>
    <svelte:fragment slot="buttons">
      <VisionButtons on:click={() => open('yorkshire')} class={yorkshireOpen ? 'bg-white/20' : ''}>📌</VisionButtons>
      <VisionButtons on:click={() => open('arabia')} class={arabiaOpen ? 'bg-white/20' : ''}>🐫</VisionButtons>
      <VisionButtons on:click={() => open('africa')} class={africaOpen ? 'bg-white/20' : ''}>🦁</VisionButtons>
      <VisionButtons on:click={() => open('global')} class={globalOpen ? 'bg-white/20' : ''}>🌍</VisionButtons>
    </svelte:fragment>

    {#if yorkshireOpen}
      <div class="z-10 flex h-full w-full flex-row items-center justify-center gap-16 will-change-transform" transition:slide={{ duration: 300, easing: cubicInOut }}>
        <Image class="w-96 self-start rounded-xl" src={ScarcityGraphImg} alt="Aquifer" />
        <div class="flex h-full w-full max-w-md flex-col items-center justify-center">
          <h1 class="text-center text-4xl font-bold text-white">Yorkshire.</h1>
          <p class="mt-4 text-center font-semibold text-white">Water Scarcity in Yorkshire - recently.</p>
          <p class="mt-4 text-center text-white">We've seen a heatwave hit Yorkshire, leading to a lot of people needing more water. This has led to the <strong>Environment Agency</strong> declaring a <strong>drought</strong> across Yorkshire.</p>
          <p class="mt-4 text-center text-white">This is happening because of <strong>climate change</strong>, which is causing more frequent and severe <strong>heatwaves</strong>, as well as increased demand for water during hot weather. Not only that, but the <strong>jet stream</strong> that brings moisture to the UK seems to have shifted north, leading to less rainfall which depletes our water systems, specifically in Yorkshire, away from the sea.</p>
        </div>
      </div>
    {/if}

    {#if arabiaOpen}
      <div class="z-10 flex h-full w-full flex-row items-center justify-center gap-16 will-change-transform" transition:slide={{ duration: 300, easing: cubicInOut }}>
        <div class="flex flex-col items-center justify-center gap-10 will-change-transform">
          <div class="flex max-w-md flex-col items-center justify-center">
            <h1 class="text-center text-4xl font-bold text-white">The Middle East</h1>
            <p class="mt-4 text-center text-white">The Middle East faces extreme water scarcity due to its dry climate, <strong>climate change</strong>, and <strong>overuse of groundwater</strong>. Over-reliance on <strong>desalination</strong> and depleting aquifers like in <strong>Saudi Arabia</strong> and <strong>Yemen</strong> make matters worse. Conflicts over shared water sources, like the <strong>Tigris</strong> and <strong>Euphrates</strong>, add to the problem.</p>
          </div>
          <figure class="mx-auto max-w-screen-sm text-center">
            <svg class="mx-auto mb-3 h-10 w-10 text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 18 14">
              <path d="M6 0H2a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3H2a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Zm10 0h-4a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3h-1a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Z" />
            </svg>
            <blockquote>
              <p class="text-xl font-medium italic text-white">"Water is the most precious resource on earth. We must preserve it, invest in it, and make sure that it is distributed equitably among our people. The future of our nation and its prosperity depends on how well we manage this vital resource."</p>
            </blockquote>
            <figcaption class="mt-6 flex items-center justify-center space-x-3">
              <Image class="h-6 w-6 rounded-full object-cover" src={SheikhImg} alt="Sheikh Mohammed bin Rashid Al Maktoum" />
              <div class="flex items-center divide-x-2 divide-white/60">
                <cite class="pr-3 font-medium text-white">Sheikh Mohammed bin Rashid Al Maktoum</cite>
                <cite class="pl-3 text-sm text-white/80">Ruler of Dubai</cite>
              </div>
            </figcaption>
          </figure>
        </div>
        <Image class="w-72 self-start rounded-3xl" src={AquiferImg} alt="Aquifer" />
      </div>
    {/if}

    {#if africaOpen}
      <div class="z-10 flex h-full w-full flex-row items-center justify-center gap-16 will-change-transform" transition:slide={{ duration: 300, easing: cubicInOut }}>
      <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div role="img" on:click={zoom} class="group relative z-50 cursor-pointer {zoomGraph ? 'scale-[1.55]' : 'scale-100'} transition-transform duration-300 ease-in-out">
          <Image class="w-96 self-start rounded-xl" src={AfricaGraphImg} alt="Graph" />
          <div class="absolute inset-0 flex items-center justify-center rounded-xl bg-black/60 opacity-0 transition-opacity duration-300 group-hover:opacity-100">
            <svg class="w-12" fill="none" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M17.5 10c0 1.71-.572 3.287-1.536 4.548l4.743 4.745a1 1 0 0 1-1.32 1.497l-.094-.083-4.745-4.743A7.5 7.5 0 1 1 17.5 10ZM10 5.5a1 1 0 0 0-1 1V9H6.5a1 1 0 1 0 0 2H9v2.5a1 1 0 1 0 2 0V11h2.5a1 1 0 1 0 0-2H11V6.5a1 1 0 0 0-1-1Z" fill="#fff" /></svg>
          </div>
        </div>
        <div class="flex flex-col items-center justify-center gap-10 will-change-transform">
          <div class="flex max-w-md flex-col items-center justify-center">
            <h1 class="text-center text-4xl font-bold text-white">Africa</h1>
            <p class="mt-4 text-center text-white">Africa is famously known for being a region with extremely low water supply. It is facing severe water scarcity due to a combination of <strong>climate change</strong>, <strong>population growth</strong>, and <strong>poor water management</strong>. Many regions are experiencing reduced rainfall, increased temperatures, and <strong>droughts</strong>, which impact agricultural production and access to drinking water. Over <strong>90%</strong> of Africa's freshwater is located in just a few countries, making access uneven. The <strong>United Nations</strong> warns that millions of people are already living in water-stressed areas, and the situation is expected to worsen (<strong>UN Water</strong>, 2020). <strong>Desalination</strong> is being explored in some coastal regions, but it's an expensive and energy-intensive solution.</p>
          </div>
        </div>
      </div>
    {/if}

    {#if globalOpen}
      <div class="z-10 flex h-full w-full flex-row items-center justify-center gap-12 px-8 will-change-transform" transition:slide={{ duration: 300, easing: cubicInOut }}>
          <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div role="img" on:click={zoom2} class="group relative z-50 cursor-pointer {zoomGraph2 ? 'scale-[1.8] translate-x-36' : 'scale-100'} transition-transform duration-300 ease-in-out">
          <Image class="w-96 self-start rounded-xl" src={GlobalImg} alt="Graph" />
          <div class="absolute inset-0 flex items-center justify-center rounded-xl bg-black/60 opacity-0 transition-opacity duration-300 group-hover:opacity-100">
            <svg class="w-12" fill="none" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M17.5 10c0 1.71-.572 3.287-1.536 4.548l4.743 4.745a1 1 0 0 1-1.32 1.497l-.094-.083-4.745-4.743A7.5 7.5 0 1 1 17.5 10ZM10 5.5a1 1 0 0 0-1 1V9H6.5a1 1 0 1 0 0 2H9v2.5a1 1 0 1 0 2 0V11h2.5a1 1 0 1 0 0-2H11V6.5a1 1 0 0 0-1-1Z" fill="#fff" /></svg>
          </div>
        </div>
        <div class="flex h-full w-full max-w-md flex-col items-center justify-center">
          <h1 class="mb-4 text-center text-4xl font-bold text-white">Globally</h1>
          <p class="mt-4 text-center text-white">Water scarcity is a growing global issue, driven by <strong>climate change</strong>, <strong>population growth</strong>, and <strong>pollution</strong>. As temperatures rise, <strong>droughts</strong> and <strong>extreme weather</strong> events are becoming more frequent, reducing freshwater availability. By 2030, it’s estimated that nearly <strong>half of the world’s population</strong> will live in water-stressed areas. <strong>Climate change</strong> is disrupting rainfall patterns and shrinking <strong>glaciers</strong>, which many countries rely on for freshwater. Meanwhile, <strong>over-extraction</strong> of groundwater and <strong>water pollution</strong> are depleting vital resources. The <strong>World Economic Forum</strong> has listed water crises as one of the top global risks. Long-term, solutions will require <strong>international cooperation</strong>, <strong>sustainable management</strong>, and technological innovations like <strong>water recycling</strong> and <strong>desalination</strong>.</p>
        </div>
        <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div role="img" on:click={zoom3} class="group relative z-50 cursor-pointer {zoomGraph3 ? 'scale-[1.8] -translate-x-36' : 'scale-100'} transition-transform duration-300 ease-in-out">
          <Image class="w-96 self-start rounded-xl" src={WaterStressImg} alt="Graph" />
          <div class="absolute inset-0 flex items-center justify-center rounded-xl bg-black/60 opacity-0 transition-opacity duration-300 group-hover:opacity-100">
            <svg class="w-12" fill="none" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M17.5 10c0 1.71-.572 3.287-1.536 4.548l4.743 4.745a1 1 0 0 1-1.32 1.497l-.094-.083-4.745-4.743A7.5 7.5 0 1 1 17.5 10ZM10 5.5a1 1 0 0 0-1 1V9H6.5a1 1 0 1 0 0 2H9v2.5a1 1 0 1 0 2 0V11h2.5a1 1 0 1 0 0-2H11V6.5a1 1 0 0 0-1-1Z" fill="#fff" /></svg>
          </div>
        </div>
      </div>
    {/if}
  </VisionWindow>

  <button
    slot="button"
    on:click
    class="relative overflow-hidden rounded-full border-white/[0.18] bg-white/25 drop-shadow backdrop-blur-xl transition-colors duration-300 ease-in-out hover:bg-white/40 focus:bg-white/40"
    on:click={() => {
      isDeepDiveCausesOpen = false;
    }}>
    <svg class="relative z-20 transition-all duration-300 ease-in-out" xmlns="http://www.w3.org/2000/svg" width="41" height="41"><path fill-rule="evenodd" fill="white" d="M22.173 20.25l6.345-6.345c.481-.481.481-1.346 0-1.923-.48-.481-1.346-.481-1.922 0l-6.346 6.345-6.345-6.345c-.481-.481-1.346-.481-1.923 0-.481.481-.481 1.346 0 1.923l6.345 6.345-6.345 6.346c-.481.48-.481 1.346 0 1.922.481.481 1.346.481 1.923 0l6.345-6.345 6.346 6.345c.48.481 1.346.481 1.922 0 .481-.48.481-1.346 0-1.922l-6.345-6.346z" /></svg></button>
</Deepdive>
