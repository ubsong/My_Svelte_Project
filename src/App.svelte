<script>
  import Header from "./Header.svelte";
  import Card from "./Card.svelte";
  import Tabs from "./Tabs.svelte";
  export let name;

  //tabs
  let items = ['Current Poll', 'Add New Poll'];
  let activeItem = 'Current Poll';
  const tabChange =(e) => {
    activeItem = e.detail;
  }

</script>

<main>
  <Header />
  <h1>스벨트 {name}!</h1>
  <p>
    Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
    how to build Svelte apps.
  </p>
  
  <Card />
  
  <Tabs {activeItem} {items} on:tabChange={tabChange}/>
  {#if activeItem === 'Current Poll'}
    <p>Poll list component goes here</p>
  {:else if activeItem === 'Add New Poll'}
    <p>new Poll form component goes here</p>
  {/if}

</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #4b19d4;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 300;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
