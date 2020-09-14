<!-- App.svelte -->

<script>
  import Tabs from "./components/Tabs.svelte";

  let tabsItems = ["Home", "About"];
  let tabsActive = "Home";

  const tabChange = (e) => (tabsActive = e.detail);
</script>

<main>
  <Tabs {tabsItems} {tabsActive} on:tabChange={tabChange} />
  {#if tabsActive === 'Home'}
    <h1>Home Page</h1>
  {:else if tabsActive === 'About'}
    <h1>About Page</h1>
  {/if}
</main>
