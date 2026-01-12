<script>
    import rainfallLogo from '../../assets/rainfall_logo.PNG'
    import rainOverlay from '../../assets/rain_overlay.PNG'
    import cloud1 from '../../assets/cloud_1.PNG'
    import cloud2 from '../../assets/cloud_2.PNG'
    import cloud3 from '../../assets/cloud_3.PNG'
    
    import cascade from '../../assets/cascade.jpeg'
    import blossom from '../../assets/blossom.png'
</script>

<div class="past-events">
    <h1>Past Events</h1>
    <p>Click each image to learn more! Both Cascade and Blossom were Atlanta events, and in the past we've partnered with organizations such as Girl Scouts and Soccer in the Streets! </p>
    <div class="clouds">
        <div class="event-container cascade">
            <img class="base" src={cloud1} alt="Cloud" />
            <div class="on-top-of-cloud">
                <a target="_blank" href="https://github.com/hackclub/cascade?tab=readme-ov-file#-cascade">
                    <img class="image-on-top" src={cascade} alt=""/>
                </a>
                <p class="label">CASCADE</p>
            </div>
        </div>
        <div class="event-container other-event">
                <img class="base" src={cloud2} alt="Cloud" />
            <div class="on-top-of-cloud">
                <p class="label">OTHER EVENT</p>
            </div>
        </div>
        <div class="event-container blossom">
            <img class="base" src={cloud3} alt="Cloud" />
            <div class="on-top-of-cloud">
                <a target="_blank" href="https://github.com/hackclub/blossom?tab=readme-ov-file#blossom-">
                    <img class="image-on-top" src={blossom} alt=""/>
                </a>
                <p class="label">BLOSSOM</p>
            </div>
        </div>
    </div>
</div>

<style>
    .past-events {
        margin-top: 150px; 
    }

    /* the below code was adapted and created with copilot. 
    I certainly tweaked things, but since CSS isn't my strong 
    suit this helped me get something down that's responsive 
    to different screen sizes */

    .clouds {
        display: grid;
        gap: 16px;
        grid-template-columns: repeat(2, 1fr);
        align-items: start;
        justify-items: center;
    }

    .event-container {
        width: clamp(240px, 35vw, 560px);
        max-width: 100%;
        display: block;
        position: relative;
        --overlay-top: 38%;
    }

    .base {
        width: 100%;
        height: auto;
        display: block;
    }

    .image-on-top {
        width: clamp(72px, 36%, 200px);
        height: auto;
        border-radius: 10px;
        display: block;
        margin: 0 auto; /* ensure block-level centering fallback */
        transition: transform 2 ease; 
    }

    .image-on-top:hover {
        transform: scale(1.15) rotate(-5deg); 
    }

    .event-container.blossom {
        grid-column: 1 / -1;
        justify-self: center;
    }

    .on-top-of-cloud {
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
        /* allow shifting the whole overlay horizontally via a per-event variable */
        transform: translateX(var(--overlay-shift-x, 0));
    }

    .event-container.blossom { --overlay-top: 30%; }
    .event-container.cascade { --overlay-top: 40%; --overlay-shift-x: 15px; }
    .event-container.other-event { --overlay-top: 40%; }

    .label {
        color: rgb(0, 93, 181);
        margin: 0;
        margin-top: -5px;
        text-align: center;
        width: 100%;
    }
</style>