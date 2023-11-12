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
  <nav>
    <h1>lovepill</h1>
    <h2>
      [{pageName}]
    </h2>
  </nav>
  <hr />
  <div class="core">
    <Taskbar />
    <div class="content">
      <div class="wrapper">
        <svelte:component this={page} />
      </div>
    </div>
  </div>
  <Webring />
</main>

<style>
  nav {
    display: flex;
    justify-content: center;
    align-items: center;
    height: min-content;
  }
  
  main {
    margin-top: 2rem;
    width: 80rem;
    gap: 1rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .content {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .core {
    height: 37.5rem;
    display: flex;
    justify-content: center;
    width: 100%;
  }

  .wrapper {
    grid-area: main;
    display: grid;
    grid-template-rows: 1;
    grid-template-columns: 1;
    flex-grow: 1;
    width: 100%;
    height: 100%;
    overflow-x: hidden;
    overflow-y: auto;
  }

  .wrapper > :global(*) {
    grid-row: 1;
    grid-column: 1;
  }

  hr {
    border: none;
    border-top: 1px dotted white;
    width: 800px;
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
</style>
