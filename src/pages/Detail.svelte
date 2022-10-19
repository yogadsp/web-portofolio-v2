<script>
  import Footer from './Footer.svelte';
  import { fade, fly } from 'svelte/transition';
  import { Fancybox } from "@fancyapps/ui";
  let pageName = "Detail";

  // json file is locate at svelte-project/public/..
  const url = '../data/dataBase.json';
  
  // make variable to call async function
  const fetchData = (async () => {
    const response = await fetch(url);
    return await response.json()
  })()

  // -1 because there are bug after click from Portfolio.svelte the value i is +1
  let i = sessionStorage.getItem('portId') - 1;

  Fancybox.bind('[data-fancybox="portfolio"]', {
    Thumbs: false,
  	Toolbar: false,

	Image: {
		zoom: false,
		click: false,
		wheel: "slide",
	},
  });


</script>

<!-- change title bar name with svelte special tags -->
<svelte:head>
  <title>Yoga Dwi Septana | {pageName}</title>
</svelte:head>

<div style="margin-bottom: 2%;"></div>
	<!-- load data JSON -->
	<!-- svelte-ignore empty-block -->
	{#await fetchData}
	{:then data}
	<div class="container" in:fade="{{duration: 450}}">

	  <div class="row">
	    <div class="col-md-12 home-content primary-font-color">
		  <a href="/portfolio" class="float-left btn btn-outline-danger" style="color: inherit">&lt;</a>
		  <h2 class="title-font primary-font-color">{data[i].title}</h2>
		  <div style="margin-bottom: 4%;"></div>
		</div>
	  </div>

	  <div class="row">
	  	<div class="col-md-12 text-justify">
	  	{@html data[i].detail}
	  	</div>
	  </div>

	  <div class="row port-container" in:fly={{y:50,delay:450}}>
	  	  {#each Array(data[i].ssNumber) as _,j} <!-- loop at data[i].ssNumber times -->
			<div class="col-md-4">
				<div class="list-port">
				  <!-- noopener and noreferrer is for security reason -->
				  <!-- https://mathiasbynens.github.io/rel-noopener/#hax -->
				  
				  <a data-fancybox="portfolio" href="/assets/img/portfolio/{data[i].name}{j+1}.png" data-caption="{data[i].imageDescription[j]}">
				    <img alt="{data[i].name}{j+1}.png" src="/assets/img/portfolio/{data[i].name}{j+1}.png">
				  </a>
				  <div class="list-port-desc">{data[i].imageDescription[j]}</div>
				</div>
			</div>
		  {/each}
		  <!-- if project name is Automatic Trash Bin Prototype -->
		  {#if data[i].id == 5}
		    <div class="col-md-4">
				<div class="list-port">
				  <iframe title="Trash Bin" src="https://drive.google.com/file/d/1UvI9nvrZ7DX82HKQSkjrhbPagVwDgkfh/preview"></iframe>
				  <div class="list-port-desc">Adding Trash Bin Location Info</div>
				</div>
			</div>

			<div class="col-md-4">
				<div class="list-port">
				  <iframe title="Trash Bin" src="https://drive.google.com/file/d/1bToH4PgOOLRisySqVOWRrz8PHFkl7YlJ/preview"></iframe>
				  <div class="list-port-desc">Sorting Organic Trash</div>
				</div>
			</div>

			<div class="col-md-4">
				<div class="list-port">
				  <iframe title="Trash Bin" src="https://drive.google.com/file/d/1lLTRVeA4Lu0JygRHw8w66jxWmd5BQvSc/preview"></iframe>
				  <div class="list-port-desc">Sorting Non-Organic Trash</div>
				</div>
			</div>
		  {/if}
	  </div>
     
	  <Footer />
	  
	</div>
	{:catch error}
      <p>Error fetch JSON data!</p>
	{/await}