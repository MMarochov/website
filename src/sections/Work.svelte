<!-- Work.svelte -->
<script>
  import WorkEntry from "../components/WorkEntry.svelte";

  let work_entries = [
    {
      title: "SEE_ICE",
      image: "images/SEE_ICE.PNG",
      description:
        "During my Masters I developed and published a paper on a method which uses deep learning to classify Sentinel-2 imagery containing marine-terminating glaciers in Greenland. Click on the link below to take a look.",
      github: "https://github.com/MMarochovDU/SEE_ICE",
      webpage: "https://doi.org/10.5194/tc-15-5041-2021",
    },
    {
      title: "OS Machine Learning Model Hub",
      image: "images/model_hub_logo.PNG",
      description:
        "I worked with the VisionAI and Research Teams at OS to create a model hub, aiming to reduce duplication of effort and facilitate increased ethical consideration, transparency, and accountability.",
      webpage: "https://nice-bay-0c89e3803.1.azurestaticapps.net/",
    },
    {
      title: "This-OS-Map-Does-Not-Exist",
      image: "images/osmap25kbowmont.svg",
      description:
        "Coming soon! I'm currently figuring out how to use a Generative Adversarial Network to create fake OS maps.",
    },
  ];
</script>

<section class="work">
  <h2>My Work</h2>
  <div class="grid-container">
    {#each work_entries as m}
      <WorkEntry
        title={m.title}
        description={m.description}
        image={m.image}
        github={m.github}
        webpage={m.webpage}
      />
    {/each}
  </div>
</section>

<style>
  .work {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 5% 0 5% 0;
  }
  .grid-container {
    max-width: 1000px;
    display: flex;
    flex-wrap: wrap;
    gap: 30px;
    justify-content: center;
  }
</style>
