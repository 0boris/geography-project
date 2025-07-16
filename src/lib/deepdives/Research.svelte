<script lang="ts">
  import BackgroundImage from '$assets/images/melodysheep/BROWN_DWARF.jpeg';
  import VerticalCarousel from '$lib/components/VerticalCarousel.svelte';
  import CarouselImg from '$lib/components/carouselImg.svelte';
  import DeepdiveCloseBtn from '$lib/components/deepdiveCloseBtn.svelte';
  import Deepdive from '$lib/layout/Deepdive.svelte';
  import type { Picture } from '$lib/types';

  const pictures: Record<string, Picture> = import.meta.glob('$assets/images/{jpg,webp}/*.{png,jpg,jpeg,webp}', {
    import: 'default',
    eager: true
  });

  const melodysheepCards = [
    { src: 'webp/Infographic.webp', alt: 'Water Scarcity - in a nutshell.' },
    { src: 'webp/ProjectedStress.webp', alt: 'Projected Water Stress by 2050.' },
    { src: 'webp/StatisticsGraphic.webp', alt: 'Water Scarcity Statistics.' },
    { src: 'jpg/ScarcityInfographic.jpg', alt: 'Freshwater Scarcity - visualized.' }
  ].sort(() => Math.random() - 0.5);

  export let isDeepDiveResearchOpen: boolean;
  let scrollProgress = 0;
</script>

<Deepdive on:scroll={(e) => (scrollProgress = e.detail)} class="" bind:isDeepDiveOpen={isDeepDiveResearchOpen}>
  <div class="fixed left-1/2 top-0 z-20 flex -translate-x-1/2 items-center justify-center">
    <h2 class="bg-cen relative mt-6 w-full bg-[url('https://www.urbanexile.net/wordpress/wp-content/uploads/2015/03/Starfield_Instancing_white_uniform.png')] bg-cover bg-clip-text text-8xl font-bold text-transparent transition-colors delay-100 duration-300 group-hover:text-black md:text-9xl">Research</h2>
  </div>
  <div class="relative flex w-full flex-shrink-0 backdrop-blur">
    <div class="relative mx-4 flex w-full items-center gap-10 md:mx-24 md:gap-24">
      <div class="relative z-20 max-w-xs text-white md:max-w-md lg:max-w-lg">
        <h3 class="mb-4 text-3xl font-bold">Understanding Water Scarcity</h3>
        <p class="text-xl leading-relaxed">This project took a long time to research. You can find the sources and bibliography in a word document, linked below.</p>
        <a href="https://heckgrammarcouk-my.sharepoint.com/:w:/g/personal/23bosmanov_heckgrammar_co_uk/EedeujM_2_VBr9mn4i8vdaoBx-iJ3sMah8PDxgtmfAJ3Wg?e=U5Tm57" target="_blank" rel="noopener noreferrer" class="inline-block rounded-md bg-white px-5 py-1.5 text-base font-semibold text-black transition-all hover:bg-white/80 mt-8">Sources and Research</a>
      </div>

      <VerticalCarousel id="melodysheep" text="All images are sourced from Google.">
        {#each melodysheepCards as card}
          <CarouselImg src={pictures[`/src/assets/images/${card.src}`]} alt={card.alt} />
        {/each}
      </VerticalCarousel>

      <div class="relative z-20 max-w-xs text-right text-white md:max-w-md lg:max-w-lg">
        <h3 class="mb-4 text-3xl font-bold">Other information</h3>
        <p class="text-xl leading-relaxed">As part of our research, we collected a variety of graphs, images, and infographics. While some of them are dotted across the website in their respective 'deep dives', the rest have been compiled here for you to see.</p>
      </div>
    </div>
    <div class="pointer-events-none absolute inset-0 z-40 h-1/3 w-full bg-gradient-to-b from-zinc-900 from-30%" />
  </div>

  <DeepdiveCloseBtn slot="button" bind:isDeepDiveOpen={isDeepDiveResearchOpen} bind:scrollProgress />
</Deepdive>
