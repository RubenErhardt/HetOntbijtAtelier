<script>
  import { onMount } from 'svelte';
  import Loader from '$lib/loader.svelte';

  let loading = true;
  let showContent = false;

  onMount(() => {
    // Simuleer laadduur
    setTimeout(() => {
      loading = false;

      // Wacht op fade-out animatie van Loader (1s)
      setTimeout(() => {
        showContent = true;
      }, 1000);
    }, 2000); // ← Simuleer 2s loading, pas aan indien nodig
  });
</script>

<!-- Loader wordt altijd getoond, maar fade-out op loading = false -->
<Loader {loading} />

<!-- Content wordt pas getoond na fade-out van loader -->
{#if showContent}
  <div class="content content-visible">
    <slot />
  </div>
{:else}
  <div class="content"></div> <!-- Zorgt dat layout niet springt -->
{/if}

<style>
.content {
  opacity: 0;
  transition: opacity 1s ease;
}

.content-visible {
  opacity: 1;
}
</style>
