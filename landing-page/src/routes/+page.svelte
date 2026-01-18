<script>
  import {onDestroy, onMount} from 'svelte';
  import DataCollection from './GrafanaDashboard.svelte';
  import GrafanaDashboard from "./GrafanaDashboard.svelte";
  import Section from './Section.svelte';

  onMount(() => {
    const sections = document.querySelectorAll('section');

    /*sections.forEach(section => {
      section.addEventListener('click', () => {
        //section.scrollIntoView({ behavior: 'smooth' });
      });
    });*/
  });


</script>

<header class="global-header">
  <img class="logo" src="logo.svg" alt="Description of the image">
  <a href="#section2" class="navbaritems">Our Idea</a>
  <a href="#section3" class="navbaritems">Our Dashboard</a>
  <a href="#section4" class="navbaritems">Our Approach</a>
  <a href="#section5" class="navbaritems">Our Learnings</a>

</header>

<main class ="mainbody">

  <Section id="section2" title="Our Idea">

  </Section>
  <Section id="section3" title="Our Dashboard">
  </Section>
  <Section id="section4" title="Our Approach">

  </Section>
  <Section id="section5" title="Our Learnings">

  </Section>


</main>





<style>
  :global(html),
  :global(body) {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
    background:  #DAD7CD  ; /* Gradient background */
    background-size: cover;
    background-attachment: fixed;
    color: black;
  }

  .navbaritems {
    margin-top: 4px;
    font-weight: bold;
    margin-right: 5px;
    text-decoration: none; /* Remove underline */
    color: black; /* Inherit color from parent */
    margin-left: 10px;
  }
  .global-header {
    position: fixed;
    display: flex;
    height: 55px;
    align-items: center; /* Center vertically */
    width: 100%;
    background-color: #A3B18A ;
  }

  .mainbody {
    margin-top: 55px;
    height: calc(100vh - 100px);
  }
  .logo {
    width: 120px;
    height: 120px;
    margin-right: 10px;
    margin-left: 30px;
  }

</style>
