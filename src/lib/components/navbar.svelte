<script>
  import Button from '$lib/components/ui/buttons.svelte';
  import { fade } from 'svelte/transition';

  let menuOpen = $state(false);
</script>

<!-- fullscreen mobile menu -->
{#if menuOpen}
  <div
    transition:fade={{ duration: 200 }}
    class="md:hidden fixed inset-0 z-40 bg-white flex flex-col"
  >
    <!-- menu content -->
    <div class="flex flex-col items-center justify-center flex-1 gap-8">
      <ul class="flex flex-col items-center gap-2">
        {#each ['Hjem', 'Om os', 'Projekter', 'Priser', 'Kontakt'] as item, i}
          <li
            in:fade={{ duration: 200, delay: 100 + i * 60 }}
            class="text-3xl font-semibold tracking-tight"
          >
            <a href="/" class="hover:text-primary transition-colors text-muted" onclick={() => menuOpen = false}>
              {item}
            </a>
          </li>
        {/each}
      </ul>

      <div
        in:fade={{ duration: 200, delay: 450 }}
        class="flex gap-3 pt-4"
      >
        <Button variant="primary" label="Kontakt os" />
        <Button variant="outline" label="Se projekter" />
      </div>
    </div>

    <!-- bottom tagline -->
    <div
      in:fade={{ duration: 200, delay: 500 }}
      class="text-center pb-10 text-sm text-gray-400"
    >
      Yderskov — Tiny houses med karakter
    </div>
  </div>
{/if}

<nav class="fixed left-0 right-0 top-0 z-50 px-6 bg-[#ffffffd9] backdrop-blur-3xl">
  <div class="max-w-[1280px] mx-auto py-3 grid grid-cols-3 items-center">

    <!-- logo -->
    <div>
      <Button variant="logo" label="Yderskov" />
    </div>

    <!-- desktop links -->
    <div class="hidden md:flex justify-center">
      <ul class="flex gap-6">
        {#each ['Hjem', 'Om os', 'Projekter', 'Priser'] as item}
          <li>
            <a href="/" class="text-sm font-medium hover:text-primary transition-colors text-muted">
              {item}
            </a>
          </li>
        {/each}
      </ul>
    </div>

    <!-- desktop right -->
    <div class="hidden md:flex gap-3 justify-end">
      <Button variant="outline" label="Se projekter" />
      <Button variant="primary" label="Kontakt os" />
    </div>

    <!-- hamburger (mobile only) -->
    <div class="md:hidden flex justify-end col-span-2">
      <button
        onclick={() => menuOpen = !menuOpen}
        aria-label="Toggle menu"
        class="w-8 h-8 flex flex-col justify-center items-center gap-0 relative"
      >
        <span class="hamburger-line" class:open={menuOpen} style="--i: 0"></span>
        <span class="hamburger-line" class:open={menuOpen} style="--i: 1"></span>
        <span class="hamburger-line" class:open={menuOpen} style="--i: 2"></span>
      </button>
    </div>

  </div>
</nav>

<style>
  .hamburger-line {
    display: block;
    width: 22px;
    height: 2px;
    background: currentColor;
    border-radius: 2px;
    margin: 3px 0;
    transform-origin: center;
    transition: transform 0.3s ease, opacity 0.3s ease, margin 0.3s ease;
  }

  /* top line → rotate 45deg */
  .hamburger-line:nth-child(1).open {
    transform: translateY(8px) rotate(45deg);
  }

  /* middle line → fade out */
  .hamburger-line:nth-child(2).open {
    opacity: 0;
    transform: scaleX(0);
  }

  /* bottom line → rotate -45deg */
  .hamburger-line:nth-child(3).open {
    transform: translateY(-8px) rotate(-45deg);
  }
</style>