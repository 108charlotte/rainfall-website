<script>
    import raindrop1 from '../../assets/raindrop_1.PNG'
    import raindrop2 from '../../assets/raindrop_2.PNG'
    import raindrop3 from '../../assets/raindrop_3.PNG'
</script>

<div id="organizers">
    <h1>Organizers</h1>
    <div class="raindrops">
        <div class="raindrop charlotte">
            <img src={raindrop1} alt="Raindrop"/>
        </div>
        <div class="raindrop shyla">
            <img src={raindrop2} alt="Raindrop"/>
        </div>
    </div>
</div>

<style>
    #organizers {
        margin-top: 100px; 
    }
    .raindrops {
        display: grid; 
        gap: 10px; 
        grid-auto-flow: column; 
    }
    .shyla img {
        width: 200px; 
    }
    .charlotte img {
        transform: translateY(10%); 
        width: 220px; 
    }
</style>