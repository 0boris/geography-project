<script lang="ts">
  import Card from '$lib/components/Card.svelte';

  export let isDeepDiveOpen: boolean;
</script>

<Card bind:isDeepDiveOpen class="group row-span-1 flex items-center justify-center text-white hover:border-white/30 md:col-span-3">
  <div class="pointer-events-none absolute inset-0 flex items-end justify-center overflow-hidden md:rounded-3xl">
    <span class="z-20 translate-y-[30%] transform select-none bg-gradient-to-b from-[#ec9c47] to-[#f2504b] bg-clip-text p-2 text-8xl font-semibold text-transparent transition-all duration-1000 ease-out group-hover:-translate-y-[80%] group-hover:scale-75 group-hover:text-white"> Consequences </span>
  </div>
  <div class="relative z-10 hidden h-full w-full overflow-hidden md:block md:rounded-3xl">
    <div class="absolute right-0 mt-3 flex translate-x-1/3 select-none text-left leading-6 tracking-tight opacity-90 shadow-2xl transition-all duration-1000 group-hover:translate-x-0">
      <div class="group relative flex w-full items-center justify-between overflow-hidden rounded-lg bg-red-900 bg-opacity-[65%] p-[1px] shadow-sm backdrop-blur-md transition-all duration-500 focus:border-red-500 focus:outline-none focus:ring-2 focus:ring-red-500 peer-checked:!bg-opacity-[100%]">
        <div class="relative w-full rounded-[calc(0.5rem-1px)] bg-[#0a0505] bg-opacity-100 p-4">
          <div class="group-[:checked+&amp;]:scale-150 absolute inset-0 max-h-[100px] max-w-[100px] rounded-full bg-gradient-to-r from-red-600 to-orange-500 blur-lg transition-all duration-500 will-change-transform group-hover:scale-150 group-active:group-hover:scale-125 group-active:group-hover:duration-200" style="transform: translate(10%, -10%) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));"></div>
          <span class="z-20 flex w-full justify-between text-center leading-5 tracking-tight"
            ><span class="relative m-0 min-w-0 basis-1/2 self-center p-0 text-left"><span class=" text-left text-2xl font-semibold leading-5 tracking-tight text-white">Critical Impact <span class="relative mt-1 block text-left text-xs font-normal tracking-normal opacity-70">2.2B people lack safe drinking water access</span></span></span>
            <span class="relative m-0 min-w-0 basis-1/2 self-center p-0 text-right">
              <span class="relative mt-1 block text-right text-xs font-normal tracking-normal text-white"><span class=" text-right text-xs leading-4 tracking-normal">828M undernourished</span> </span>
            </span>
          </span>
        </div>
      </div>
    </div>
    <form>
      <div class="absolute -left-4 top-7 max-w-xs translate-y-2/3 -rotate-90 opacity-80">
        <input type="radio" id="HealthImpact" name="consequence" class="hidden" value="HealthImpact" />
        <label for="HealthImpact" class="group relative flex h-24 w-full cursor-pointer select-none items-center justify-between overflow-hidden rounded-lg bg-orange-800 p-4 shadow-2xl backdrop-blur-md transition-all duration-500 hover:scale-105 focus:border-orange-500 focus:outline-none focus:ring-2 focus:ring-orange-500 active:scale-50 active:hover:scale-100 peer-checked:scale-95 peer-disabled:pointer-events-none peer-disabled:cursor-default peer-disabled:hover:scale-100">
          <div class="absolute inset-0 max-h-[100px] max-w-[100px] transform rounded-full bg-gradient-to-r from-orange-600 to-red-600 blur-lg transition-all duration-500 will-change-transform group-active:group-hover:duration-200 group-[:checked+&]:scale-[600%]" style="transform: translate(100%, 200%) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));"></div>
          <span class=" z-20 flex w-full justify-center text-center leading-5 tracking-tight md:flex-col md:items-stretch md:justify-between"><span class="relative m-0 min-w-0 basis-1/2 p-0 text-left leading-5 tracking-tight"><span class=" text-left text-lg font-semibold leading-5 tracking-tight text-white">Health Crisis <span class="relative mt-1 block text-left text-xs font-normal tracking-normal opacity-70">Disease, malnutrition, child mortality</span></span></span> <span class="relative m-0 min-w-0 basis-1/2 p-0 text-right leading-5 tracking-tight"></span></span>
        </label>
      </div>
      <button type="button" class="absolute bottom-10 right-4 inline-flex cursor-pointer select-none justify-center rounded-md border border-yellow-600 bg-yellow-700 px-4 py-2 text-sm font-medium text-white opacity-80 shadow-lg transition-all duration-500 hover:border-yellow-500 hover:bg-yellow-600 hover:text-white focus:ring-transparent focus:ring-offset-0 active:scale-90">Explore Impact</button>
    </form>
    <div class="absolute bottom-[5.625rem] right-20 inline-flex select-none items-center rounded-full border border-solid border-red-400 border-opacity-80 bg-red-600 bg-opacity-20 px-2.5 py-0.5 text-xs font-medium uppercase tracking-normal text-red-200 text-opacity-90 opacity-80 shadow-lg">Crisis</div>
  </div>
</Card>
