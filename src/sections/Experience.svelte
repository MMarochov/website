<script>
  // Imports
  import ExperienceEntry from "../components/ExperienceEntry.svelte";

  const experience = [
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

<div id="container">
  <h2>My Experience</h2>
  <div id="experience">
    {#each experience as e}
      <ExperienceEntry
        open={e.open}
        org={e.org}
        role={e.role}
        months={e.months}
        years={e.years}
        description={e.description}
      />
    {/each}
    <svg height="100%" width="4">
      <line
        y1="0"
        y2="5%"
        stroke-dasharray="2.5,2.5"
        stroke="#000"
        stroke-width="4"
      />
      <line y1="5%" y2="95%" stroke="#000" stroke-width="4" />
      <line
        y1="95%"
        y2="100%"
        stroke-dasharray="2.5,2.5"
        stroke="#000"
        stroke-width="4"
      />
    </svg>
  </div>
</div>

<style>
  #container {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  #experience {
    width: 60%;
    position: relative;
    display: inline-block;
    align-self: center;
  }

  svg {
    position: absolute;
    left: 137px;
    top: 8px;
  }

  :global(main.dark-mode) line {
    stroke: #d7e3f5;
	}
</style>
