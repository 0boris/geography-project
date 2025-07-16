<script lang="ts">
  import WaterStressImage from '$assets/images/webp/Consequences.webp';
  import Card from '$lib/components/Card.svelte';
  import DeepdiveCloseBtn from '$lib/components/deepdiveCloseBtn.svelte';
  import Image from '$lib/components/image.svelte';
  import Deepdive from '$lib/layout/Deepdive.svelte';
  import type { Picture } from '$lib/types';
  import gsap from 'gsap/dist/gsap';
  import { onMount } from 'svelte';

  const WaterStressImg = WaterStressImage as unknown as Picture;

  let drops: { x: number; y: number; delay: number; duration: number }[] = [];
  
  for (let i = 0; i < 30; i++) {
    drops.push({
      x: Math.random() * 100,
      y: -10,
      delay: Math.random() * 3,
      duration: 2 + Math.random() * 2
    });
  }

  export let isDeepDiveConsequencesOpen: boolean;

  onMount(() => {
    const dropElements = document.querySelectorAll('.water-drop');
    dropElements.forEach((drop, index) => {
      gsap.set(drop, { y: -50 });
      gsap.to(drop, {
        y: window.innerHeight + 50,
        duration: drops[index]?.duration || 3,
        delay: drops[index]?.delay || 0,
        repeat: -1,
        ease: "none"
      });
    });
  });
</script>

<Deepdive bind:isDeepDiveOpen={isDeepDiveConsequencesOpen}>
  <div class="relative flex justify-center items-center h-full w-screen overflow-hidden antialiased">
    
    <Image 
      src={WaterStressImg} 
      class="absolute inset-0 h-full w-full object-cover opacity-70" 
      alt="Water stress and consequences" 
    />
    
    <div class="absolute inset-0 bg-black/50"></div>
    
    {#each drops as drop, i}
      <div 
        class="water-drop absolute h-8 w-1 rounded-full bg-blue-400 opacity-60 z-20"
        style="left: {drop.x}%; filter: blur(1px);"
      ></div>
    {/each}

    <div class="relative z-30 flex h-full w-full justify-center items-center p-8 overflow-y-auto">
      <div class="max-w-7xl w-full space-y-8">
        
        <div class="grid grid-cols-1 gap-6 md:grid-cols-3">
          <Card class="bg-black/20 backdrop-blur-md border-red-500/30">
            <div class="p-6">
              <div class="mb-4 text-center">
                <div class="mx-auto mb-2 h-16 w-16 rounded-full bg-red-500/80 flex items-center justify-center">
                  <span class="text-2xl">🏥</span>
                </div>
                <h3 class="text-xl font-bold text-white">Health Crisis</h3>
              </div>
              <div class="text-center">
                <div class="stat-number text-3xl font-bold text-red-400">2.2 billion</div>
                <p class="text-sm text-gray-300">people lack safe drinking water</p>
              </div>
            </div>
          </Card>

          <Card class="bg-black/20 backdrop-blur-md border-yellow-500/30">
            <div class="p-6">
              <div class="mb-4 text-center">
                <div class="mx-auto mb-2 h-16 w-16 rounded-full bg-yellow-500/80 flex items-center justify-center">
                  <span class="text-2xl">⚰️</span>
                </div>
                <h3 class="text-xl font-bold text-white">Deadly Impact</h3>
              </div>
              <div class="text-center">
                <div class="stat-number text-3xl font-bold text-yellow-400">3 million</div>
                <p class="text-sm text-gray-300">deaths annually from water-related diseases</p>
              </div>
            </div>
          </Card>

          <Card class="bg-black/20 backdrop-blur-md border-orange-500/30">
            <div class="p-6">
              <div class="mb-4 text-center">
                <div class="mx-auto mb-2 h-16 w-16 rounded-full bg-orange-500/80 flex items-center justify-center">
                  <span class="text-2xl">🚨</span>
                </div>
                <h3 class="text-xl font-bold text-white">Future Crisis</h3>
              </div>
              <div class="text-center">
                <div class="stat-number text-3xl font-bold text-orange-400">67%</div>
                <p class="text-sm text-gray-300">of world population facing shortages by 2025</p>
              </div>
            </div>
          </Card>
        </div>

        <!-- Main Content Sections -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          
          <!-- The Hidden Burden -->
          <Card class="bg-black/30 backdrop-blur-md border-purple-500/30">
            <div class="p-8">
              <div class="flex items-center mb-6">
                <div class="h-12 w-12 rounded-full bg-purple-500/80 flex items-center justify-center mr-4">
                  <span class="text-xl">👧</span>
                </div>
                <h2 class="text-2xl font-bold text-white">The Hidden Burden</h2>
              </div>
              <div class="space-y-4 text-gray-200">
                <p class="leading-relaxed">
                  Water scarcity takes its <span class="text-purple-400 font-semibold">greatest toll on women and children</span>, 
                  who are often responsible for collecting water. When sources are distant, children—especially girls—miss school.
                </p>
                <p class="leading-relaxed">
                  <span class="text-red-400 font-semibold">Carrying water for miles</span> creates enormous physical burden 
                  and exposes children to safety risks and exploitation during their dangerous journeys.
                </p>
                <div class="bg-purple-900/30 p-4 rounded-lg border-l-4 border-purple-400">
                  <p class="text-sm italic">
                    "Less water access = less time for education = perpetual cycle of poverty"
                  </p>
                </div>
              </div>
            </div>
          </Card>

          <!-- The Vanishing World -->
          <Card class="bg-black/30 backdrop-blur-md border-green-500/30">
            <div class="p-8">
              <div class="flex items-center mb-6">
                <div class="h-12 w-12 rounded-full bg-green-500/80 flex items-center justify-center mr-4">
                  <span class="text-xl">🌍</span>
                </div>
                <h2 class="text-2xl font-bold text-white">Ecosystem Collapse</h2>
              </div>
              <div class="space-y-4 text-gray-200">
                <p class="leading-relaxed">
                  <span class="text-green-400 font-semibold">Half of the world's wetlands</span> have vanished since 1900. 
                  These ecosystems support countless species and provide crucial services like flood control.
                </p>
                <p class="leading-relaxed">
                  The <span class="text-red-400 font-semibold">Aral Sea</span> - once the world's 4th largest lake - 
                  has shrunk to a fraction of its size, creating an ecological catastrophe that shortened lives and destroyed livelihoods.
                </p>
                <div class="grid grid-cols-2 gap-4 mt-4">
                  <div class="text-center">
                    <div class="text-2xl font-bold text-green-400">75%</div>
                    <div class="text-xs text-gray-400">wetlands destroyed</div>
                  </div>
                  <div class="text-center">
                    <div class="text-2xl font-bold text-red-400">50%+</div>
                    <div class="text-xs text-gray-400">water systems stressed</div>
                  </div>
                </div>
              </div>
            </div>
          </Card>

          <!-- The Stark Reality -->
          <Card class="bg-black/30 backdrop-blur-md border-blue-500/30 lg:col-span-2">
            <div class="p-8">
              <div class="flex items-center mb-6">
                <div class="h-12 w-12 rounded-full bg-blue-500/80 flex items-center justify-center mr-4">
                  <span class="text-xl">💧</span>
                </div>
                <h2 class="text-2xl font-bold text-white">The Stark Reality</h2>
              </div>
              <div class="grid md:grid-cols-3 gap-6 text-gray-200">
                <div class="space-y-3">
                  <h3 class="text-lg font-semibold text-blue-400">Water Paradox</h3>
                  <p class="text-sm leading-relaxed">
                    Despite Earth being 70% water, only <span class="text-cyan-400 font-semibold">3% is freshwater</span> - 
                    and two-thirds of that is frozen in glaciers, leaving less than 1% for all human needs.
                  </p>
                </div>
                <div class="space-y-3">
                  <h3 class="text-lg font-semibold text-yellow-400">Disease & Death</h3>
                  <p class="text-sm leading-relaxed">
                    <span class="text-red-400 font-semibold">2.4 billion people</span> lack proper sanitation, 
                    exposing them to cholera, typhoid, and other deadly waterborne diseases that claim millions of lives.
                  </p>
                </div>
                <div class="space-y-3">
                  <h3 class="text-lg font-semibold text-orange-400">Agricultural Crisis</h3>
                  <p class="text-sm leading-relaxed">
                    Agriculture consumes <span class="text-orange-400 font-semibold">70% of freshwater</span> but wastes much through inefficiency, 
                    while climate change disrupts rainfall patterns globally.
                  </p>
                </div>
              </div>
            </div>
          </Card>

        </div>
      </div>
    </div>

    <div class="absolute bottom-10 left-10 text-white/80 z-30">
      <p class="text-sm italic font-medium">The ripple effects spread far beyond water...</p>
    </div>
    
    <div class="absolute top-10 right-10 text-white/80 z-30">
      <p class="text-sm italic font-medium">Every drop counts. Every action matters.</p>
    </div>

  </div>

  <DeepdiveCloseBtn slot="button" bind:isDeepDiveOpen={isDeepDiveConsequencesOpen} />
</Deepdive>
