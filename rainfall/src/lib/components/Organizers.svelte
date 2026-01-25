<script>
    import raindrop1 from '../../assets/raindrop_1.png'
    import raindrop2 from '../../assets/raindrop_2.png'
    import charlotte from '../../assets/charlotte.jpg'
    import shyla from '../../assets/charlotte.jpg'

    import ImageCard from './ImageCard.svelte'
</script>

<div id="organizers">
    <h1>Organizers</h1>
    <div class="raindrops">
        <ImageCard baseImage={raindrop1} baseImageSize={"90%"} overlayTop={"32%"} overlayShiftX={"-2%"} overlayImageSize={"34%"}>
            <img src={charlotte} alt="Charlotte at the Rockefeller center in NYC"/>
            <p class="name">Charlotte Woodrum</p>
            <p class="bio">Aspiring software or ML engineer who enjoys exploring new technologies! </p>
            <a href="https://www.charlottewoodrum.dev/" target="_blank">Personal website</a>
            <a href="https://www.linkedin.com/in/charlotte-woodrum-557900370/" target="_blank">LinkedIn</a>
        </ImageCard>
        <ImageCard baseImage={raindrop2} baseImageSize={"100%"} overlayTop={"70%"} overlayShiftX={"-5%"} overlayImageSize={"34%"}>
            <img src="" alt=""/>
            <p class="name">Shyla Singal</p>
            <p class="bio">A short about me</p>
        </ImageCard>
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

    .name {
        margin-top: -5px;
        font-size: 4vw;
        color: rgb(0, 30, 57);
        font-weight: 700;
        line-height: 1.1;
    }

    a, .bio {
        font-size: 2.2vw;
        margin: 0;
        text-align: center;
        width: 60%; 
    }

    .bio {
        margin-top: -30px;
        color: rgb(0, 50, 97);
    }

    a {
        color: rgb(255, 255, 255);
        text-decoration: underline;
        background: rgb(8, 106, 142);
        width: 120px;
        border-radius: 10px;
        font-size: 2vw;
        display: inline-block;
        padding: 6px 8px;
    }
</style>