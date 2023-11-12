<script>

  import Webring from './lib/Webring.svelte';
  import Taskbar from './lib/Taskbar.svelte';

  import Main from './pages/Main.svelte';
  import About from './pages/About.svelte';
  import Projects from './pages/Projects.svelte';
  import Radio from './pages/Radio.svelte';

  import router from "page.js";

  let page;
  let pageName = "main";

  router("/", () => (
    page = Main, pageName = "main"
  ));
  router("/about", () => (
    page = About, pageName = "about"
  ));
  router("/projects", () => (
    page = Projects, pageName = "projects"
  ));
  router("/radio", () => (
    page = Radio, pageName = "radio"
  ));
  router.start();
</script>

<svelte:head>
  <title>lovepill</title>
  <link rel="icon" href="pixelstar-pixel.gif" type="image/gif">
</svelte:head>

<main>
  <h1>
    lovepill
  </h1>
  <h2>
    [{pageName}]
  </h2>
  <hr />
  <container>
    <Taskbar />
    <div class="divider"></div>
    <svelte:component this={page} />
    <!-- <div class="wrapper">
      <svelte:component this={page} />
    </div> -->
  </container>
  <Webring />
</main>

<style>
  hr {
    border: none;
    border-top: 1px dotted white;
    max-width: 800px;
  }

  h1 {
    font-family: "Redaction 50";
    font-size: 35px;
    display: inline;
  }

  h2 {
    font-family: "Redaction 30";
    font-size: 20px;
    display: inline;
  }

  .divider {
    border: none;
    border-left: 1px dotted white;
    width: 50%;
    min-height: 600px;
    max-width: 1px;
  }

  container {
    display: flex;
    justify-content: center;
  }

  /* .wrapper {
    grid-area: main;
    display: grid;
    grid-template-rows: 1;
    grid-template-columns: 1;
    flex-grow: 1;
  }

  .wrapper > :global(*) {
    grid-row: 1;
    grid-column: 1;
  } */
</style>
