<!-- Work.svelte -->
<script>

import WorkEntry from "../components/WorkEntry.svelte";

let team_members = [
        {
            title: "SEE_ICE",
            image: "images/SEE_ICE.PNG",
            description: "During my Masters I developed and published a paper on a method which uses deep learning to classify Sentinel-2 imagery containing marine-terminating glaciers in Greenland. Click on the link below to take a look.",
            icons: "images/Github",
            href: "https://github.com/MMarochov/SEE_ICE"
        },
        {
            title: "OS Machine Learning Model Hub",
            image: "images/model_hub_logo.PNG",
            description: "I worked with the VisionAI and Research Teams at OS to create a model hub, aiming to reduce duplication of effort and facilitate increased ethical consideration, transparency, and accountability.",
            icons: "",
            href: "https://nice-bay-0c89e3803.1.azurestaticapps.net/"
        },
        {
            title: "This-OS-Map-Does-Not-Exist",
            image: "images/osmap25kbowmont.PNG",
            description: "Coming soon! I'm currently figuring out how to use a Generative Adversarial Network to create fake OS maps.",
            icons: "",
            href: ""
        }           
    ]
</script>

<div class="meet-the-team">
    <h2>My Work</h2>
    <div class="grid-container">
        {#each team_members as m}
        <WorkEntry title={m.title} description={m.description} image={m.image} icons={m.icons} href={m.href}/>
        {/each}


    </div>
</div>

<style>

    h2 {
        padding-top: 120px;
    }
    .meet-the-team {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .grid-container {
        display: inline-grid;
        gap: 2em 2em;
        grid-template-columns: 31% 31% 31%;
        grid-template-rows: auto auto auto;
        justify-items: center;
        margin-top: 30px;
        margin-bottom: 30px;
    }
    /*  GO FULL WIDTH BELOW 480 PIXELS */
    @media only screen and (max-width: 950px) {
        .grid-container { grid-template-columns: 100%; grid-template-rows: repeat(5, auto); gap: 1em 0px;}
    }
</style>

