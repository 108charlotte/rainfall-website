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
        <ImageCard maxWidth={"400px"} baseImage={raindrop1} baseImageSize={"90%"} overlayTop={"32%"} overlayShiftX={"-2%"} overlayImageSize={"34%"}>
            <img src={charlotte} alt="Charlotte at the Rockefeller center in NYC"/>
            <p class="name">Charlotte Woodrum</p>
            <p class="bio">Aspiring software or ML engineer who enjoys building cool projects! </p>
            <a href="https://www.linkedin.com/in/charlotte-woodrum-557900370/" target="_blank">LinkedIn</a>
        </ImageCard>
        <ImageCard maxWidth={"400px"} baseImage={raindrop2} baseImageSize={"100%"} overlayTop={"70%"} overlayShiftX={"-5%"} overlayImageSize={"34%"}>
            <img src="" alt=""/>
            <p class="name">Shyla Singal</p>
            <p class="bio">A short about me</p>
            <a href="" target="_blank">LinkedIn</a>
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
        font-size: 3vw;
        width: 24vw; 
        color: rgb(0, 30, 57);
        font-weight: 700;
        line-height: 1.1;
        align-items: center; 
        justify-content: center; 
        margin-bottom: 3vh; 
    }

    a, .bio {
        font-size: clamp(10px, 2vw, 20px); 
        margin: 0;
        text-align: center;
    }

    .bio {
        margin-top: -30px;
        color: rgb(0, 50, 97);
        width: 60%; 
    }

    a {
        color: rgb(255, 255, 255);
        text-decoration: underline;
        display: inline-block;
        transition: background 0.2s ease; 
        width: auto; 
    }

    a:hover {
        color: rgb(196, 234, 247);
    }
</style>