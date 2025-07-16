<script lang="ts">
  import Card from '$lib/components/Card.svelte';

  export let isDeepDiveOpen: boolean;
</script>

<Card bind:isDeepDiveOpen class="group row-span-1 flex items-center justify-center text-white hover:border-white hover:bg-white hover:text-black md:col-span-3">
  <div class="flex h-full w-full items-center justify-center bg-cover object-cover p-5">
    <span class="text-7xl font-extrabold">SOLUTIONS</span>
  </div>
  <div class="absolute -top-2 left-0 text-6xl font-bold text-black group-hover:text-zinc-300 transition-colors duration-300">
    HOPE.HOPE.HOPE.HOPE.HOPE.HOPE.HOPE.HOPE.<br />HOPE.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;HOPE.<br />HOPE.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;HOPE.<br />HOPE.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;HOPE.<br />HOPE.HOPE.HOPE.HOPE.HOPE.HOPE.HOPE.HOPE.<br />
  </div>
</Card>
