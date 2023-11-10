<script>

  import Counter from './lib/Counter.svelte';
  import Webring from './lib/Webring.svelte';
  import Taskbar from './lib/Taskbar.svelte';

  import Main from './pages/Main.svelte';
  import About from './pages/About.svelte';
  import Projects from './pages/Projects.svelte';
  import Radio from './pages/Radio.svelte';


  let page = Main;

  function swap(swapTo) {
    page = swapTo;
  }
</script>

<svelte:head>
  <title>lovepill</title>
</svelte:head>

<main>
  <svelte:component this={page} />
  <Webring />
</main>

<style>
  
</style>
