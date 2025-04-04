<script>
  import Taskbar from './lib/Taskbar.svelte';

  import Overview from './pages/Overview.svelte';
  import Vision from './pages/Vision.svelte';
  import Team from './pages/Team.svelte';
  import Postmortem from './pages/Postmortem.svelte';

  import router from "page.js";

  let page;
  let pageName = "Overview";

  router("/", () => (
    page = Overview, pageName = "Overview"
  ));
  router("/team", () => (
    page = Team, pageName = "Team"
  ));
  router("/vision", () => (
    page = Vision, pageName = "Vision Statement"
  ));
  router("/postmortem", () => (
    page = Postmortem, pageName = "Postmortem"
  ));
  router.start();
</script>

<svelte:head>
  <title>BarterBee</title>
  <link rel="icon" href="overlay_transparent.png" type="image/png">
</svelte:head>

<main>
  <nav>
    <h1>BarterBee</h1>
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
