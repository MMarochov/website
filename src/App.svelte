<script>
  import NavBar from "./components/NavBar.svelte";
  import Name from "./components/Name.svelte";
  import ScrollToTop from "./components/ScrollToTop.svelte";
  import ScrollArrow from "./components/ScrollArrow.svelte";
  import Social from "./components/Social.svelte";
  import Timeline from "./components/Timeline.svelte";
  import Work from "./components/Work.svelte";
  import About from "./sections/About.svelte";
  import { darkMode } from "./stores/darkMode.js";
  const experiences = [
    {
      open: true,
      org: "Ordnance Survey",
      role: "Graduate Technical Consultant",
      months: "September - present",
      years: "2022/23",
      description:
        "As part of the Developer Experience team within Consultancy and Technical Services at OS, I've worked on shaping a critical national dataset that will underpin the census and now I'm making an interactive webmap for a famous person!",
    },
    {
      open: false,
      org: "Ordnance Survey",
      role: "Graduate Data Scientist",
      months: "April - September",
      years: "2022",
      description:
        "After six months on the Ordnance Survey Graduate Scheme, I joined the Rapid Prototyping Team and got thrown in at the deep end of data science with a bunch of super proficient developers. Having the chance to work on a diverse array of  projects led me to enhance a variety of skills, from Python programming to agile development. On my first day in the team I didn't have the foggiest clue how to build a website, but now I've made this one, yey! Creating cool prototypes using geospatial data in a fast-paced (and fun) environment made the RPT my favourite placement.",
    },
    {
      open: false,
      org: "Ordnance Survey",
      role: "Graduate Research Scientist",
      months: "September - March",
      years: "2021/22",
      description:
        "For my first placement on the OS Grad scheme I joined the Research and Innovation teams. I focused on advancing OS' efforts to incorporate ethical practice in their workflows which use geospatial data and artificial intelligence (GeoAI). Some of the highlights were running an external-facing hybrid workshop on practical tools in GeoAI ethics, and creating a Model Hub for OS's machine learning algorithms.",
    },
    {
      open: false,
      org: "Durham University",
      role: "M. Sc. (by research) Geography",
      months: "October - January",
      years: "2019 - 2021",
      description:
        "The crux of my postgraduate research was to develop a method which uses deep learning for semantic segmentation of Sentinel-2 satellite imagery containing marine-terminating glaciers in Greenland. I published a paper in one of the top peer-reviewed glaciology journals, presented at the EGU2020: Sharing Geoscience Online conference, and demonstrated in undergraduate Remote Sensing practicals. To see what I made, checkout the Work section below.",
    },
    {
      open: false,
      org: "Durham University",
      role: "B. Sc. Geography",
      months: "October - July",
      years: "2016 - 2019",
      description:
        "I just love Geography. So I skidaddled off and got a B.Sc. degree at Durham University. I specialised in glaciology in my final year and wrote a dissertation on the evolution of supraglacial meltwater features on an ice shelf in East Antarctica. This degree took me all over the UK, to Portugal and to Iceland!",
    },
  ];
  const workEntries = [
    {
      title: "SEE_ICE",
      image: "images/SEE_ICE.PNG",
      description:
        "During my Masters I developed and published a method which uses deep learning to classify Sentinel-2 imagery containing marine-terminating glaciers in Greenland. Here's some links:",
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
      image: "images/osmap_blur.PNG",
      description:
        "Coming soon! I'm currently figuring out how to use a Generative Adversarial Network to create fake OS maps.",
    },
    {
      title: "Mapping the Irish Sea Ice Stream",
      image: "images/bgs_map.PNG",
      description: "I helped make a map published by BGS. It shows the sea floor geomorphology offshore of Angelesy - including features such as Drumlins and iceberg plough marks left by the last ice sheet.",
      webpage: "https://www.bgs.ac.uk/news/new-geological-map-of-offshore-anglesey-released/"
    },
    {
      title: "Seal A Better Place",
      image: "images/seal_a_better_place.gif",
      description: "This November I took part in the #30DayMapChallenge. This seal gif is the favourite map I made. I used the MovingPandas and GeoPandas Python libraries to analyse the movement of the seal.",
      github: "https://github.com/MMarochov/sealz"
    }
  ];
</script>

<main class={$darkMode ? "dark-mode" : ""}>
  <article class="container">
    <NavBar />
    <section id="landing-page">
      <Name>
        <span slot="intro">It's-a me,</span>
        <span slot="name">Melio</span>
        <!-- <span slot="typed"></span> -->
      </Name>
      <About>
        I'm Mel Marochov, a trainee geospatial data scientist and developer at
        Ordnance Survey. In my spare time I love skateboarding, wild swimming,
        and climbing! Over the past year or so I've had the chance to learn a
        lot of interesting stuff from very talented people, ranging from Python
        and web dev to data visualisation and GeoAI ethics... but I'm only just
        beginning to scratch the surface.
      </About>
      <Social />
      <ScrollArrow href="#experience" />
    </section>
    <ScrollToTop />
    <section id="experience">
      <h2>Experience</h2>
      <!-- To edit experience entries on the timeline, edit the experiences variable declared above -->
      {#each experiences as e}
        <Timeline
          open={e.open}
          org={e.org}
          role={e.role}
          months={e.months}
          years={e.years}
          description={e.description}
        />
      {/each}
    </section>
    <section class="work">
      <h2>Work</h2>
      <div class="grid-container">
        {#each workEntries as w}
          <Work
            image={w.image}
            title={w.title}
            description={w.description}
            github={w.github}
            webpage={w.webpage}
          />
        {/each}
      </div>
    </section>
  </article>
</main>

<style>
  :global(main.dark-mode) {
    background-color: #1e4b70;
    color: #d7e3f5;
  }

  .container {
    text-align: center;
    width: 100%;
    margin: 0 auto;
    max-width: 960px;
  }

  section h2 {
    font-family: "Permanent Marker", cursive;
    font-size: 1.6rem;
  }

  #landing-page {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    position: relative;
  }

  #experience {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 5% 0 5%;
  }

  .work {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 5% 0 5% 0;
    padding: 5% 0 15%;
  }

  .grid-container {
    max-width: 960px;
    display: flex;
    flex-wrap: wrap;
    gap: 30px;
    justify-content: center;
  }

  :global(body),
  :global(html) {
    margin: 0;
  }

  :global(main) {
    background: radial-gradient(
        circle at 65% 8%,
        rgba(255, 0, 0, 0.3),
        rgba(255, 0, 0, 0) 80.71%
      ),
      radial-gradient(
        circle at 6.7% 60%,
        rgba(149, 116, 252, 0.6),
        rgba(0, 0, 255, 0) 70.71%
      ),
      radial-gradient(
        circle at 95% 35%,
        rgba(116, 252, 227, 0.7),
        rgba(0, 255, 0, 0) 70.71%
      ),
      radial-gradient(
        circle at 95% 100%,
        rgba(255, 0, 0, 0.25),
        rgba(255, 0, 0, 0) 80.71%
      ),
      radial-gradient(
        circle at 8% 100%,
        rgba(116, 252, 227, 0.7),
        rgba(0, 255, 0, 0) 70.71%
      ),
      white;
  }

  @media only screen and (max-width: 1100px) {
    #landing-page {
      max-width: 670px;
      margin: auto;
    }
  }

  @media only screen and (max-width: 670px) {
    #landing-page {
      max-width: 500px;
      margin: auto;
    }
  }
</style>
