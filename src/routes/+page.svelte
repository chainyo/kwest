<script>
    import Header from '../components/Header.svelte';
    import Footer from '../components/Footer.svelte';
    import RoadmapCard from '../components/RoadmapCard.svelte';

    let loading = true;
    let roadmaps = [];
  </script>
  
  <div class="flex flex-col min-h-screen">
    <Header />

    {#if loading}
        <div class="flex place-content-center text-center hero-content">
            <span class="loading loading-infinity loading-lg"></span>
        </div>
    {/if}
    <main class="flex-grow p-4 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-4">
    {#if !loading}
        {#each roadmaps as title (title)}
            <RoadmapCard {title} />
        {/each}
    
        <!-- Plus button -->
        <button class="btn btn-neutral">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="h-6 w-6 mx-auto">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4" />
            </svg>
        </button>
        {/if}
    </main>
  
    <Footer />
  </div>
  
  
