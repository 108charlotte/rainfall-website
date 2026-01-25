<script>
    import rainfallLogo from '../../assets/rainfall_logo.PNG'
    import rainOverlay from '../../assets/rain_overlay.PNG'
    import cloud1 from '../../assets/cloud_1.PNG'
    import cloud2 from '../../assets/cloud_2.PNG'
    import cloud3 from '../../assets/cloud_3.png'
    
    import cascade from '../../assets/cascade.jpeg'
    import blossom from '../../assets/blossom.png'
    import evergreen from '../../assets/evergreen.jpeg'

    import ImageCard from './ImageCard.svelte'; 
</script>

<div class="past-events">
    <h1>Past Events</h1>
    <p>Click each image to learn more! Both Cascade and Blossom were Atlanta events, and in the past we've partnered with organizations such as Girl Scouts and Soccer in the Streets! </p>
    <div class="clouds">
        <ImageCard baseImage={cloud1} overlayTop={"25%"} overlayShiftX={"6%"} overlayImageSize={"40%"}>
            <a target="_blank" href="https://github.com/hackclub/cascade?tab=readme-ov-file#-cascade">
                <img class="image-on-top" src={cascade} alt="A web development workshop at cascade"/>
            </a>
            <p class="label">CASCADE</p>
        </ImageCard>
        <ImageCard baseImage={cloud2} overlayTop={"32%"} overlayImageSize={"40%"} overlayShiftX={"8%"}>
            <a target="_blank" href="https://github.com/hackclub/evergreen?tab=readme-ov-file#-evergreen">
            <img class="image-on-top" src={evergreen} alt="A participant learning circuit board design with EasyEDA at Evergreen"/>
        </a>
            <p class="label">EVERGREEN</p>
        </ImageCard>
        <div class="blossom-container">
            <ImageCard baseImage={cloud3} overlayTop={"25%"} baseImageSize={"100%"} overlayImageSize={"40%"}>
                <a target="_blank" href="https://github.com/hackclub/blossom?tab=readme-ov-file#blossom-">
                    <img class="image-on-top" src={blossom} alt="Participants checking in at Blossom"/>
                </a>
                <p class="label">BLOSSOM</p>
            </ImageCard>
        </div>
    </div>
</div>

<style>
    .past-events {
        margin-top: 150px; 
    }

    @media (min-width: 700px) {
        .past-events {
            margin-top: 0px; 
        }
    }

    .clouds {
        display: grid;
        gap: 16px;
        grid-template-columns: repeat(2, 1fr);
        align-items: start;
        justify-items: center;
        justify-content: center; 
    }

    .blossom-container {
        grid-column: 1 / -1;
        justify-self: center;
        margin-top: -20vh; 
    }

    .label {
        color: rgb(0, 93, 181);
        margin: 0;
        margin-top: -5px;
        text-align: center;
        width: 100%;
    }
</style>