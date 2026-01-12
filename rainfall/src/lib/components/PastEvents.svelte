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
    <p>Click the image to learn more! Both Cascade and Blossom were Atlanta events, and in the past we've partnered with organizations such as Girl Scouts and Soccer in the Streets! </p>
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
    .clouds {
        display: grid;
        gap: 16px;
        grid-template-columns: repeat(2, 1fr);
        align-items: start;
        justify-items: center;
    }

    .base {
        width: 300px; 
    }

    .image-on-top {
        width: 100px; 
        border-radius: 10px; 
    }

    /* copilot code to center blossom cloud on 2nd grid row */
    .event-container.blossom {
      grid-column: 1 / -1;
      justify-self: center;
    }

    .blossom .on-top-of-cloud {
      transform: translate(0%, -150%); 
    }

    .cascade .on-top-of-cloud {
        transform: translate(5%, -200%); 
    }

    .other-event .on-top-of-cloud {
        transform: translate(0%, -800%); 
    }

    .label {
        color: rgb(0, 93, 181); 
        transform: translateY(-60%); 
    }

    .blossom {
        transform: translateY(-40%); 
    }
</style>