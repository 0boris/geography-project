<script lang="ts">
  import LightningImage from '$assets/images/causes/lightning.png';
  import Card from '$lib/components/Card.svelte';
  import Image from '$lib/components/image.svelte';
  import type { Picture } from '$lib/types';

  const LightningImg = LightningImage as unknown as Picture;

  export let isDeepDiveOpen: boolean;
</script>

<Card bind:isDeepDiveOpen class="group row-span-2 flex items-center bg-black md:col-span-2">
  <div class="absolute top-0 -z-10 h-0 w-full bg-gradient-to-b from-[#156184]/60 to-[#0AA9F2]/60 transition-all duration-300 ease-in group-hover:h-full" />
  <div class="flex h-full w-full flex-col items-center">
    <h2 class="relative mt-6 w-full bg-gradient-to-b from-[#ec9c47] to-[#f2504b] bg-clip-text text-center text-6xl font-semibold text-transparent transition-colors delay-100 duration-300 group-hover:text-white">Causes</h2>
    <Image src={LightningImg} loading="eager" class="w-96 select-none pt-52 transition-all duration-300 group-hover:pt-24" alt="Waving Memoji" />
  </div>
</Card>
