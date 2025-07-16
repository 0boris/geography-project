<script lang="ts">
  import CodingImage from '$assets/images/jpg/Coding.jpg';
  import DeepdiveCloseBtn from '$lib/components/deepdiveCloseBtn.svelte';
  import Image from '$lib/components/image.svelte';
  import Deepdive from '$lib/layout/Deepdive.svelte';
  import Window from '$lib/layout/Window.svelte';
  import type { Picture } from '$lib/types';
  import { Draggable } from 'gsap/dist/Draggable';
  import gsap from 'gsap/dist/gsap';
  import { onMount } from 'svelte';
  import { Highlight } from 'svelte-highlight';
  import markdown from 'svelte-highlight/languages/markdown';

  const CodingImg = CodingImage as unknown as Picture;

  export let isDeepDiveCreditsOpen: boolean;

  onMount(() => {
    gsap.registerPlugin(Draggable);
  });

  function initializeDrag() {
    Draggable.create('#codingwindow', {
      bounds: document.getElementById('codingcontainer'),
      dragClickables: false,
      edgeResistance: 0.5,
      trigger: '#topbarcodingwindow'
    });
  }
</script>

<Deepdive bind:isDeepDiveOpen={isDeepDiveCreditsOpen} on:introend={initializeDrag}>
  <div class="flex h-full w-screen">
    <Image src={CodingImg} class="absolute aspect-[4_/_3] h-full w-full select-none object-cover md:-left-1/3 md:top-1/2 md:h-auto md:-translate-y-1/2" alt="Coding" />
    <div id="codingcontainer" class="absolute -left-1/2 flex h-full w-full translate-x-1/2 items-center justify-center">
      <Window id="codingwindow" placeholder="credits.." easteregg={true}>
        <Highlight class="whitespace-pre-wrap bg-transparent leading-[22.5px] tracking-[.1px]" language={markdown} code={`# 👨🏻‍💻 Boris\nHi. I helped out with the project by making this website and did the research for the causes of our issue - water scarcity.\n\n## Akain\n Hi, I helped out with getting the graphs, images and charts, and with the info for the consequences.\n\n### Roshen\n Hallo, I helped gather information about the solutions.`} />
      </Window>
    </div>
    <div class="w-[200dvw]"></div>
  </div>

  <DeepdiveCloseBtn slot="button" bind:isDeepDiveOpen={isDeepDiveCreditsOpen} />
</Deepdive>
