<script>
  import { onMount } from 'svelte'
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import About from './lib/components/About.svelte'
  import PastEvents from './lib/components/PastEvents.svelte'
  import Sponsors from './lib/components/Sponsors.svelte'
  import Organizers from './lib/components/Organizers.svelte'
  import Contact from './lib/components/Contact.svelte'
  import Footer from './lib/components/Footer.svelte'

  // assets
  import rainfallLogo from './assets/rainfall_logo.PNG'
  import rainOverlay from './assets/rain_overlay.PNG'

  // copilot code to create parallax scroll effect
  // how far (in px) to move the overlay up initially — set between -100 and -400
  let baseOffset = -300; // change this to -100 .. -400 as you like

  // parallax multiplier
  const speed = 0.12;

  let overlayOffset = baseOffset;
  let raf = null;

  function handleScroll() {
    if (raf) return;
    raf = requestAnimationFrame(() => {
      // dynamic part based on scroll
      const dynamic = window.scrollY * speed;
      // combine base and dynamic; optionally clamp to a range so it never goes too far
      overlayOffset = Math.max(-400, Math.min(-100, baseOffset + dynamic));
      raf = null;
    });
  }

  onMount(() => {
    window.addEventListener('scroll', handleScroll, { passive: true })
    return () => window.removeEventListener('scroll', handleScroll)
  })
</script>

<main>
  <img src={rainfallLogo} alt="Rainfall Logo" width="300" />
  <img src={rainOverlay} alt="" aria-hidden="true" class="page-overlay" style="transform: translate3d(0, {overlayOffset}px, 0)" />
  <About/>
  <PastEvents/>
  <Sponsors/>
  <Organizers/>
  <Contact/>
  <Footer/>
</main>