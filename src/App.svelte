<script>
  import NavBar from "./components/NavBar.svelte";
  import Name from "./components/Name.svelte";
  import ScrollToTop from "./components/ScrollToTop.svelte";
  import ScrollArrow from "./components/ScrollArrow.svelte";
  import Social from "./components/Social.svelte";
  import About from "./sections/About.svelte";
  import Experience from "./sections/Experience.svelte";
  import Work from "./sections/Work.svelte";
  import { darkMode } from "./stores/darkMode.js";
  const experiences = [
    {
      open: true,
      org: "Ordnance Survey",
      role: "Graduate Data Scientist",
      months: "April - September",
      years: "2022",
      description:
        "My second placement on the Graduate scheme at Ordnance Survey saw me joining the Rapid Prototyping Team and getting thrown in at the deep end of data science. Having the chance to work on a diverse array of  projects has led me to enhance a variety of skills, from Python programming to agile development. On my first day in the team I didn't have the foggiest clue how to build a website, but now I've made this one, and discovered a new passion in the process! Creating cool prototypes using geospatial data in a fast-paced (and fun) environment has made this my favourite placement so far.",
    },
    {
      open: false,
      org: "Ordnance Survey",
      role: "Graduate Research Scientist",
      months: "September - March",
      years: "2021/22",
      description:
        "For my first placement on the OS Grad scheme I joined the Research and Innovation teams. In this placement I focused on advancing OS' efforts to incorporate ethical practice in their workflows which use geospatial data and artificial intelligence (GeoAI). Some of the highlights were running an external-facing hybrid workshop on practical tools in GeoAI ethics, and creating a Model Hub for OS' re-usable machine learning algorithms.",
    },
    {
      open: false,
      org: "Durham University",
      role: "M. Sc. (by research) Geography",
      months: "October - January",
      years: "2019 - 2021",
      description:
        "The crux of my postgraduate research was to develop a method which uses deep learning for semantic segmentation of Sentinel-2 satellite imagery containing marine-terminating glaciers in Greenland. I published a paper in one of the top peer-reviewed glaciology journals, presented at the EGU2020: Sharing Geoscience Online conference, and demonstrated in undergraduate Remote Sensing practicals. To see what I made, checkout the Work section below!",
    },
    {
      open: false,
      org: "Durham University",
      role: "B. Sc. Geography",
      months: "October - July",
      years: "2016 - 2019",
      description:
        "I pursued my passion for Geography by undertaking a B.Sc. degree at Durham University, specialising in glaciology in my final year and writing a dissertation on the evolution of supraglacial meltwater features on an ice shelf in East Antarctica. This degree took me all over the UK, to Portugal and to Iceland, and to top it all off I was awarded The Willimott Prize for graduating with the second highest grade in my year.",
    },
  ];
</script>

<main>
  <NavBar />
  <section id="landing-page">
    <Name>
      <span slot="intro">It's-a me,</span>
      <span slot="name">Melio</span>
      <!-- <span slot="typed"></span> -->
    </Name>
    <About>
      I'm Mel Marochov, a trainee geospatial data scientist and developer at
      Ordnance Survey. In my spare time I love skateboarding, wild swimming, and
      climbing! At work I've been learning stuff from really talented people,
      from a wee bit of Python to a fair amount of web dev... but mainly just an
      outrageous number of keyboard shortcuts.
    </About>
    <Social />
    <ScrollArrow href="#experience" />
  </section>
  <ScrollToTop />
  <section id="experience">
    <h2>Experience</h2>
    <!-- To edit experience entries, edit the experiences variable declared above -->
    {#each experiences as e}
      <Experience>
        <span slot="year">{e.years}</span>
        <span slot="months">{e.months}</span>
        <span slot="role">{e.role}</span>
        <span slot="org">{e.org}</span>
        <span slot="description">{e.description}</span>
      </Experience>
    {/each}
  </section>
  <section id="work">
    <Work />
  </section>
</main>

<style>
  #landing-page {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    position: relative;
  }

  #experience {
    padding-top: 10%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  #work {
    padding-top: 10%;
  }
  :global(body) {
    padding: 20px;
  }
  :global(body),
  :global(html) {
    margin: 0;
    height: fit-content;
  }

  :global(html) {
    background: radial-gradient(
        circle at 50% 20%,
        rgba(255, 0, 0, 0.3),
        rgba(255, 0, 0, 0) 70.71%
      ),
      radial-gradient(
        circle at 6.7% 80%,
        rgba(149, 116, 252, 0.7),
        rgba(0, 0, 255, 0) 70.71%
      ),
      radial-gradient(
        circle at 75% 55%,
        rgba(116, 252, 227, 0.6),
        rgba(0, 255, 0, 0) 70.71%
      ),
      radial-gradient(
        circle at 45% 100%,
        rgba(255, 0, 110, 0.4),
        rgba(0, 0, 255, 0) 70.71%
      ),
      white;
  }

  main {
    text-align: center;
    width: 100%;
    max-width: 960px;
    margin: 0 auto;
  }
  @media only screen and (max-width: 1050px) {
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
