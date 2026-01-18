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

  // parallax multiplier
  const speed = 0.2;

  // visual scale for the overlay image (zoom). Increase to "zoom in" the overlay
  // so the visible area is larger and the overlay appears to scroll for longer.
  // Try values like 1 (no zoom), 1.4, 1.6, 2.0 etc.
  let overlayScale = 1.2;

  // how far (in px) to move the overlay up initially — set between -100 and -400
  let baseOffset = -800; // change this to -100 .. -400 as you like

  // horizontal nudge (px). Positive moves right, negative moves left.
  // Use this to offset the overlay horizontally from center.
  let overlayShiftX = -120; // px

  // start the overlay at the base offset
  let overlayOffset = baseOffset;
  let raf = null;

  function handleScroll() {
    if (raf) return;
    raf = requestAnimationFrame(() => {
      // dynamic part based on scroll
      const dynamic = window.scrollY * speed;
      // increase multiplier so the overlay moves farther per scroll unit
      const dynamicMultiplier = 1.5;

      // combine base and dynamic. Widen the clamp so the overlay can move for a
      // longer portion of the scroll. Adjust the min/max to taste.
      overlayOffset = Math.max(-1200, Math.min(200, baseOffset + dynamic * dynamicMultiplier));
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
  <img
    src={rainOverlay}
    alt=""
    aria-hidden="true"
    class="page-overlay"
    style="--overlay-shift-x: {overlayShiftX}px; transform: translate3d(calc(-50% + var(--overlay-shift-x)), {overlayOffset}px, 0) scale({overlayScale});"
  />
  <About/>
  <PastEvents/>
  <Sponsors/>
  <Organizers/>
  <Contact/>
  <Footer/>
</main>

<style>
  /* Make the overlay scale around the top center and hint the browser to optimize transforms */
  .page-overlay {
    position: fixed;
    left: 50%;
    top: 0;
    transform-origin: center top;
    will-change: transform;
    pointer-events: none;
  /* horizontal translate is applied inline so we can nudge it via --overlay-shift-x */
  /* (inline style includes translate3d(calc(-50% + var(--overlay-shift-x)), y, 0) ) */
  /* You can change the overlay width if you want it to cover more than the viewport width */
    width: 120vw; /* slightly wider so zoom doesn't clip at the edges */
    max-width: none;
    height: auto;
  }
</style>