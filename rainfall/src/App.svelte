<script>
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import About from './lib/components/About.svelte'
  import PastEvents from './lib/components/PastEvents.svelte'
  import Sponsors from './lib/components/Sponsors.svelte'
  import Organizers from './lib/components/Organizers.svelte'

  // assets
  import rainfallLogo from './assets/rainfall_logo.PNG'
  import rainOverlay from './assets/rain_overlay.PNG'
  import cloud1 from './assets/cloud_1.PNG'
  import cloud2 from './assets/cloud_2.PNG'
  import cloud3 from './assets/cloud_3.PNG'
  import raindrop1 from './assets/raindrop_1.PNG'
  import raindrop2 from './assets/raindrop_2.PNG'
  import raindrop3 from './assets/raindrop_3.PNG'
</script>

<main>
  <img src={rainfallLogo} alt="Rainfall Logo" width="300" />

  <About/>
  <PastEvents/>
  <Sponsors/>
  <Organizers/>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
