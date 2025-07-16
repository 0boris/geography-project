<script lang="ts">
  import BackgroundImage from '$assets/images/jpg/SolutionsBackground.jpg';
  import DeepdiveCloseBtn2 from '$lib/components/deepdiveCloseBtn2.svelte';
  import Image from '$lib/components/image.svelte';
  import ProgressBar from '$lib/components/progressBar.svelte';
  import Deepdive from '$lib/layout/Deepdive.svelte';
  import Card from '$lib/components/Card.svelte';
  import type { Picture } from '$lib/types';

  const Background: Picture = BackgroundImage as unknown as Picture;

  export let isDeepDiveSolutionsOpen: boolean;
  let scrollProgress = 0;
  let spaceMusic: HTMLAudioElement;
  let volume = 0.3;
</script>

<Deepdive on:scroll={(e) => (scrollProgress = e.detail)} class="" bind:isDeepDiveOpen={isDeepDiveSolutionsOpen}>
  <Image class="fixed inset-0 h-full w-full bg-fixed object-cover object-center brightness-[40%]" src={Background} alt="Brown Dwarf" />
  <div class="fixed left-1/2 top-0 z-20 flex -translate-x-1/2 items-center justify-center">
    <h2 class="relative mt-6 w-full bg-[url('https://www.urbanexile.net/wordpress/wp-content/uploads/2015/03/Starfield_Instancing_white_uniform.png')] bg-cover bg-clip-text bg-center text-8xl font-bold text-transparent transition-colors delay-100 duration-300 group-hover:text-black md:text-9xl">Solutions.</h2>
  </div>
  <div class="relative flex flex-shrink-0 backdrop-blur">
    <div class="relative mx-4 flex w-full items-center gap-10 md:mx-24 md:gap-24">
      <p class="relative z-20 max-w-7xl text-4xl font-semibold text-white"><span class="font-bold">The global water crisis requires urgent action - there's still time</span> to implement meaningful solutions before reaching absolute water scarcity. <br /> Through research and innovation, we can secure water resources for future generations.</p>
      <Card class="bg-black/30 p-8">
        <div class="relative z-50 text-center">
          <p class="mb-4 max-w-3xl text-2xl text-white">At least 50% of the planet's population - 4 billion people - deal with water shortfalls at least one month of the year. By 2025, 1.8 billion people will face what the FAO calls "absolute water scarcity. Solutions are within reach with innovative thinking and collaboration.</p>
          <figure class="mx-auto max-w-screen-md text-center">
            <svg class="mx-auto mb-3 h-10 w-10 text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 18 14">
              <path d="M6 0H2a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3H2a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Zm10 0h-4a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3h-1a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Z" />
            </svg>
            <blockquote>
              <p class="text-2xl font-medium italic text-white">"Solutions are within reach with innovative thinking, greater political commitment and collaboration."</p>
            </blockquote>
            <figcaption class="mt-6 flex items-center justify-center space-x-3">
              <div class="flex items-center divide-x-2 divide-neutral-700">
                <cite class="pr-3 font-medium text-white">Leticia Carvalho, UNEP</cite>
              </div>
            </figcaption>
          </figure>
        </div>
      </Card>
      <Card class="bg-black/30 p-8">
        <div class="relative z-50 text-center">
          <p class="mb-4 max-w-3xl text-2xl text-white">Key solutions include protecting natural water systems, improving agricultural efficiency (which uses 70% of freshwater), fixing infrastructure leaks, and deploying smart technologies. Countries like Australia are pioneering water-efficient practices that could save billions globally.</p>
          <figure class="mx-auto max-w-xs text-center lg:max-w-screen-md">
            <svg class="mx-auto mb-3 h-10 w-10 text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 18 14">
              <path d="M6 0H2a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3H2a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Zm10 0h-4a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3h-1a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Z" />
            </svg>
            <blockquote>
              <p class="text-2xl font-medium italic text-white">"Annual investments of $8 billion needed to meet water goals by 2030, but water reforms could save $2B by 2030."</p>
            </blockquote>
            <figcaption class="mt-6 flex items-center justify-center space-x-3">
              <div class="flex items-center divide-x-2 divide-neutral-700">
                <cite class="pr-3 font-medium text-white">Asian Development Bank & Australian Water Report</cite>
              </div>
            </figcaption>
          </figure>
        </div>
      </Card>
    </div>
    <div class="pointer-events-none absolute inset-0 z-40 h-2/6 w-full bg-gradient-to-b from-black from-45%" />
  </div>
  <div class="relative flex flex-shrink-0 backdrop-blur">
    <div class="relative mx-4 flex w-full items-center gap-10 md:mx-24 md:gap-24">
      <Card class="bg-black/30 p-8">
        <div class="relative z-50 text-center">
          <p class="mb-4 max-w-3xl text-2xl text-white">The Middle East and North Africa (MENA) region accounts for nearly half the world's desalination capacity, making it the largest desalination market globally. Over 300 million people worldwide now depend on desalinated water for some or all of their daily needs.</p>
          <figure class="mx-auto max-w-screen-md text-center">
            <svg class="mx-auto mb-3 h-10 w-10 text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 18 14">
              <path d="M6 0H2a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3H2a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Zm10 0h-4a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3h-1a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Z" />
            </svg>
            <blockquote>
              <p class="text-2xl font-medium italic text-white">"These countries have a high dependence on desalination because there is not really an alternative."</p>
            </blockquote>
            <figcaption class="mt-6 flex items-center justify-center space-x-3">
              <div class="flex items-center divide-x-2 divide-neutral-700">
                <cite class="pr-3 font-medium text-white">Shannon McCarthy, International Desalination Association</cite>
              </div>
            </figcaption>
          </figure>
        </div>
      </Card>
      <Card class="bg-black/30 p-8">
        <div class="relative z-50 text-center">
          <p class="mb-4 max-w-3xl text-2xl text-white">Australia faces unique challenges with water consumption routinely exceeding freshwater supply capacity. The country's average annual rainfall is around 470mm per year, well below the global average, with predictions suggesting this could halve in coming decades due to climate change.</p>
          <figure class="mx-auto max-w-xs text-center lg:max-w-screen-md">
            <svg class="mx-auto mb-3 h-10 w-10 text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 18 14">
              <path d="M6 0H2a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3H2a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Zm10 0h-4a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3h-1a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Z" />
            </svg>
            <blockquote>
              <p class="text-2xl font-medium italic text-white">"Per capita water consumption averages 100,000 litres per person - that's 340 litres per person per day."</p>
            </blockquote>
            <figcaption class="mt-6 flex items-center justify-center space-x-3">
              <div class="flex items-center divide-x-2 divide-neutral-700">
                <cite class="pr-3 font-medium text-white">Australian Water Usage Statistics</cite>
              </div>
            </figcaption>
          </figure>
        </div>
      </Card>
      <Card class="bg-black/30 p-8">
        <div class="relative z-50 text-center">
          <p class="mb-4 max-w-3xl text-2xl text-white">Smart water metering technology delivers unprecedented potential for behavioral change. Real-time data collection and analysis can drive significant water consumption reductions while increasing customer satisfaction and community engagement across utility networks.</p>
          <figure class="mx-auto max-w-screen-md text-center">
            <svg class="mx-auto mb-3 h-10 w-10 text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 18 14">
              <path d="M6 0H2a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3H2a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Zm10 0h-4a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3h-1a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Z" />
            </svg>
            <blockquote>
              <p class="text-2xl font-medium italic text-white">"Smart water meters encourage water consumption reduction, anywhere from 1-8% annually, while increasing customer awareness."</p>
            </blockquote>
            <figcaption class="mt-6 flex items-center justify-center space-x-3">
              <div class="flex items-center divide-x-2 divide-neutral-700">
                <cite class="pr-3 font-medium text-white">Advizzo Behavioral Data Science</cite>
              </div>
            </figcaption>
          </figure>
        </div>
      </Card>
    </div>
    <div class="pointer-events-none absolute inset-0 z-40 h-2/6 w-full bg-gradient-to-b from-black from-45%" />
  </div>

  <div class="relative flex flex-shrink-0 backdrop-blur">
    <div class="relative mx-4 flex w-full items-center gap-10 md:mx-24 md:gap-24">
      <Card class="bg-black/30 p-8">
        <div class="relative z-50 text-center">
          <p class="mb-4 max-w-3xl text-2xl text-white">Asia requires immediate action to strengthen water security through political commitment and preventive diplomacy. The region faces mounting pressure from climate change impacts on water availability, requiring forward-looking investment and far-sighted policies beyond short-term responses.</p>
          <figure class="mx-auto max-w-screen-md text-center">
            <svg class="mx-auto mb-3 h-10 w-10 text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 18 14">
              <path d="M6 0H2a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3H2a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Zm10 0h-4a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3h-1a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Z" />
            </svg>
            <blockquote>
              <p class="text-2xl font-medium italic text-white">"The vast majority of water-related problems plaguing Asia are solvable through environmentally and politically sustainable water management."</p>
            </blockquote>
            <figcaption class="mt-6 flex items-center justify-center space-x-3">
              <div class="flex items-center divide-x-2 divide-neutral-700">
                <cite class="pr-3 font-medium text-white">Asia Water Security Report</cite>
              </div>
            </figcaption>
          </figure>
        </div>
      </Card>
      <Card class="bg-black/30 p-8">
        <div class="relative z-50 text-center">
          <p class="mb-4 max-w-3xl text-2xl text-white">Inadequate water supply and sanitation costs the MENA region approximately $21 billion per year in economic losses, including healthcare costs, lost productive time, and premature mortality. If current trends continue, 60% of the region will face extremely high water stress by 2040.</p>
          <figure class="mx-auto max-w-xs text-center lg:max-w-screen-md">
            <svg class="mx-auto mb-3 h-10 w-10 text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 18 14">
              <path d="M6 0H2a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3H2a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Zm10 0h-4a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h4v1a3 3 0 0 1-3 3h-1a1 1 0 0 0 0 2h1a5.006 5.006 0 0 0 5-5V2a2 2 0 0 0-2-2Z" />
            </svg>
            <blockquote>
              <p class="text-2xl font-medium italic text-white">"By 2050, climate-related water scarcity will cost the region 6 to 14% of its GDP."</p>
            </blockquote>
            <figcaption class="mt-6 flex items-center justify-center space-x-3">
              <div class="flex items-center divide-x-2 divide-neutral-700">
                <cite class="pr-3 font-medium text-white">World Bank MENA Water Report</cite>
              </div>
            </figcaption>
          </figure>
        </div>
      </Card>
    </div>
    <div class="pointer-events-none absolute inset-0 z-40 h-2/6 w-full bg-gradient-to-b from-black from-45%" />
  </div>

  <DeepdiveCloseBtn2 on:click={() => spaceMusic.pause()} class="bg-black" slot="button" bind:isDeepDiveOpen={isDeepDiveSolutionsOpen} bind:scrollProgress />
  <ProgressBar slot="progress" bind:scrollProgress class="from-white via-white/90 to-white/20" />
  <div class="group relative" slot="extra">
    <div class="absolute -top-4 left-1/2 mb-10 flex -translate-x-1/2 -translate-y-1/2 scale-50 items-center justify-center rounded-lg bg-white opacity-0 transition-all duration-300 group-hover:-translate-y-full group-hover:scale-100 group-hover:opacity-100">
      <input type="range" min="0" max="1" step="0.01" bind:value={volume} class="mx-2 py-2 accent-black" />
    </div>
    <button
      type="button"
      class="relative z-10 rounded-full bg-white text-black"
      on:click={() => {
        if (spaceMusic.paused) {
          spaceMusic.play();
          volume = 0.3;
        } else {
          spaceMusic.pause();
          volume = 0;
        }
        if (spaceMusic.muted) {
          spaceMusic.muted = false;
          volume = 0.3;
        } else {
          spaceMusic.muted = true;
          volume = 0;
        }
      }}>
      <svg class="p-2" width="41" height="41" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        {#if volume === 0}
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5.586 15H4a1 1 0 01-1-1v-4a1 1 0 011-1h1.586l4.707-4.707C10.923 3.663 12 4.109 12 5v14c0 .891-1.077 1.337-1.707.707L5.586 15z" clip-rule="evenodd" />
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2" />
        {:else}
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15.536 8.464a5 5 0 010 7.072m2.828-9.9a9 9 0 010 12.728M5.586 15H4a1 1 0 01-1-1v-4a1 1 0 011-1h1.586l4.707-4.707C10.923 3.663 12 4.109 12 5v14c0 .891-1.077 1.337-1.707.707L5.586 15z" />
        {/if}
      </svg>
    </button>
  </div>
  <audio bind:this={spaceMusic} bind:volume class="hidden" loop autoplay src="/assets/audio/mp3/Sights_of_Space_Bside_01_mp3.mp3" />
</Deepdive>
