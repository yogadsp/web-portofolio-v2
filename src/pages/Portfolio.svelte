<script>
  import Footer from './Footer.svelte';
  import { fade, fly } from 'svelte/transition';
  let pageName = "Portfolio";

  // json file is locate at svelte-project/public/..
  const url = './data/dataBase.json';
  
  // make variable to call async function
  const fetchData = (async () => {
    const response = await fetch(url);
    return await response.json()
  })()

  let indeks = 0;

  function getId(i){
    // get element id with class "item"
    indeks = document.getElementsByClassName("item")[i].id;

    // save id to cookies or session in php
    sessionStorage.setItem('portId', indeks);
  }

</script>

<!-- change title bar name with svelte special tags -->
<svelte:head>
    <title>Yoga Dwi Septana | {pageName}</title>
</svelte:head>

<div style="margin-bottom: 2%;"></div>

<!-- call fetchData async function -->
{#await fetchData}
  <!-- make loading text or animation -->
{:then data}

<div class="container" in:fade="{{duration: 450}}"> <!-- start container -->
  <div class="row">
    <div class="col-md-12 home-content primary-font-color">
      <h1 class="title-font primary-font-color">My Portfolio</h1>
      <div style="margin-bottom: 4%;"></div>
    </div>
  </div>

  <!-- body of portfolio list -->
  <div class="row port-container">
      <!-- loop until end data "i" increment -->
      {#each data as item, i }
          <div class="col-md-4" in:fly={{y:50,delay:450}}>
            <div class="list-port desc-font">
              <a class="item" id="{item.id}" href="portfolio/detail" on:click={() => getId(i)}>
                <img alt="{item.title}" src="assets/img/portfolio/{item.thumbnail}">
                <div class="desc-port">
                  <b>{item.title}</b>
                </div>
              </a>
              {item.description}
            </div>
          </div>
      {/each}
  </div>

  <Footer />
  
</div><!-- end container -->

{:catch error}
  <p>Error fetch JSON data!</p>
{/await}