<script>
    import raindrop1 from '../../assets/raindrop_1.PNG'
    import raindrop2 from '../../assets/raindrop_2.PNG'
    import charlotte from '../../assets/charlotte.jpg'
    import shyla from '../../assets/charlotte.jpg'
</script>

<div id="organizers">
    <h1>Organizers</h1>
    <div class="raindrops">
        <div class="raindrop charlotte">
            <img class="base" src={raindrop1} alt="Raindrop"/>
            <div class="on-top-of-image">
                <img src={charlotte} alt="Charlotte at the Rockefeller center in NYC"/>
                <p class="name">Charlotte Woodrum</p>
                <p class="bio">Aspiring software or ML engineer who enjoys exploring new technologies! </p>
                <a href="https://www.charlottewoodrum.dev/" target="_blank">Personal website</a>
                <a href="https://www.linkedin.com/in/charlotte-woodrum-557900370/" target="_blank">LinkedIn</a>
            </div>
        </div>
        <div class="raindrop shyla">
            <img class="base" src={raindrop2} alt="Raindrop"/>
            <div class="on-top-of-image">
                <img src="" alt=""/>
                <p class="name">Shyla Singal</p>
                <p class="bio">A short about me</p>
            </div>
        </div>
    </div>
</div>

<style>
    #organizers {
        margin-top: 100px; 
    }

    /* the below code was adapted and created with copilot. 
    I certainly tweaked things, but since CSS isn't my strong 
    suit this helped me get something down that's responsive 
    to different screen sizes */

    .raindrops {
        display: grid;
        gap: 16px;
        grid-template-columns: repeat(2, 1fr);
        align-items: start;
        justify-items: center;
    }

    .raindrop {
        /* allow larger raindrops while remaining responsive */
        width: clamp(240px, 40vw, 800px);
        max-width: 100%;
        display: block;
        position: relative;
        --overlay-top: 38%;
        /* default image size (percentage of raindrop width) */
        --overlay-image-size: 30%;
    }

    .base {
        width: 100%;
        height: auto;
        display: block;
    }

    .on-top-of-image img {
        /* size the overlay image relative to the raindrop using a CSS variable
           so it automatically scales when you increase the raindrop size */
        width: var(--overlay-image-size, 30%);
        min-width: 120px;
        max-width: 360px;
        height: auto;
        border-radius: 10px;
        display: block;
        margin: 0 auto; /* ensure block-level centering fallback */
        transition: transform 250ms ease;
    }

    .on-top-of-image img:hover {
        transform: scale(1.15) rotate(-5deg); 
    }

    .on-top-of-image {
        /* make the overlay full-width so percent-based image sizes are
            directly proportional to the cloud container, and center children */
        position: absolute;
        left: 0;
        right: 0;
        top: var(--overlay-top, 38%);
        display: flex;
        flex-direction: column;
        align-items: center;
            gap: 8px;
        pointer-events: auto;
        width: 100%;
        text-align: center;
          /* allow shifting the whole overlay horizontally via a per-event variable
              (use percent for a responsive shift or px for absolute) */
          transform: translateX(var(--overlay-shift-x, 0%));
    }

     /* Per-raindrop variables. Use --overlay-shift-x (percent or px) so it
         matches the transform above. */
    .raindrop.charlotte { --overlay-top: 32%; --overlay-shift-x: -2%; --overlay-image-size: 34%; }
    .raindrop.shyla { --overlay-top: 70%; --overlay-shift-x: -5%; --overlay-image-size: 34%; }

    .charlotte .on-top-of-image img {
        border-top-left-radius: 80px; 
        border-top-right-radius: 50px; 
    }

    .name {
        margin-top: -5px; 
        font-size: 20px; 
        color: rgb(0, 30, 57);
        font-weight: 700; 
    }

    a, .bio {
        font-size: 14px; 
        margin: 0;
        text-align: center;
        width: 180px;
    }

    .bio {
        margin-top: -20px;
        color: rgb(0, 50, 97);
    }

    a {
        color: rgb(255, 255, 255);
        text-decoration: underline; 
        background: rgb(8, 106, 142); 
        width: 120px; 
        border-radius: 10px; 
    }
</style>