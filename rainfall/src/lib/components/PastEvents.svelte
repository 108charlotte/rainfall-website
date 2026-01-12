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
    <div class="clouds">
        <div class="event-container cascade">
            <img class="base" src={cloud1} alt="Cloud" />
            <a target="_blank" href="https://github.com/hackclub/cascade?tab=readme-ov-file#-cascade">
                <img class="image-on-top" src={cascade} alt=""/>
            </a>
            <span class="label">CASCADE</span>
        </div>
        <div class="event-container other-event">
            <img class="base" src={cloud2} alt="Cloud" />
            <span class="label">OTHER EVENT</span>
        </div>
        <div class="event-container blossom">
            <img class="base" src={cloud3} alt="Cloud" />
            <a target="_blank" href="https://github.com/hackclub/blossom?tab=readme-ov-file#blossom-">
                <img class="image-on-top" src={blossom} alt=""/>
            </a>
            <span class="label">BLOSSOM</span>
        </div>
    </div>
</div>

<style>
    .clouds {
        display: grid;
        gap: 10px;
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    }
    .event-container {
        position: relative;
        overflow: hidden;
        display: block;
    }
    .cascade {
        position: relative;
        overflow: hidden;
        display: block;
    }
    .cascade .base {
        display: block;
        width: 100%;
        height: auto;
    }
    .image-on-top {
        position: absolute;
        left: 50%;
        top: 50%;
        width: 40%; 
        height: auto;
        z-index: 2;
        opacity: 0.95;
        border-radius: 10px; 
    }
    .cascade .image-on-top {
        transform: translate(-30%, -30%);
    }
    .blossom .image-on-top {
        transform: translate(-50%, -60%);
    }
    .other-event .label {
        transform: translate(-50%, -350%); 
    }
    .blossom .label {
        transform: translate(-60%, -300%); 
    }
    .cascade .label {
        transform: translate(-40%, -200%);
    }
    .label {
        z-index: 3; 
        position: absolute;
        left: 50%;
        top: 50%;
        color: #0c6c9d; 
        /* make the label decorative for pointer events so clicks go to the link below */
        pointer-events: none;
    }
</style>