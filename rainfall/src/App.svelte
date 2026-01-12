<script>
  import { onMount } from 'svelte'
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

  // copilot script to create a minimal parallax effect for the background minimal parallax: move overlay at reduced speed relative to scroll
  let overlayOffset = 0
  let raf = null

  function handleScroll() {
    if (raf) return
    raf = requestAnimationFrame(() => {
      overlayOffset = window.scrollY * 0.35
      raf = null
    })
  }

  onMount(() => {
    window.addEventListener('scroll', handleScroll, { passive: true })
    return () => window.removeEventListener('scroll', handleScroll)
  })
</script>

<main>
  <img src={rainfallLogo} alt="Rainfall Logo" width="300" />
  <img src={rainOverlay} alt="" aria-hidden="true" class="page-overlay" style="transform: translateY({overlayOffset}px);" />
  <About/>
  <PastEvents/>
  <Sponsors/>
  <Organizers/>
  <h1>Contact</h1>
  <p>You can contact us at charlotte.m.woodrum@gmail.com or _________! </p>
</main>