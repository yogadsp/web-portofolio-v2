<script>
  import Footer from './Footer.svelte';
  import { fade, fly } from 'svelte/transition';
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

</script>

<!-- change title bar name with svelte special tags -->
<svelte:head>
  <title>Yoga Dwi Septana | {pageName}</title>
</svelte:head>

<div style="margin-bottom: 2%;"></div>
	<!-- load data JSON -->
	{#await fetchData}
	{:then data}
	<div class="container" in:fade="{{duration: 450}}">

	  <div class="row">
	    <div class="col-md-12 home-content">
		  <h2 class="title-font">{data[i].title}</h2>
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
				  <a target="_blank" rel="noopener noreferrer" href="/assets/img/portfolio/{data[i].name}{j+1}.png">
				    <img src="/assets/img/portfolio/{data[i].name}{j+1}.png">
				  </a>
				</div>
			</div>
		  {/each}
		  {#if data[i].id == 5}
		    <div class="col-md-4">
				<div class="list-port">
				  <iframe src="https://drive.google.com/file/d/1UvI9nvrZ7DX82HKQSkjrhbPagVwDgkfh/preview"></iframe>
				</div>
			</div>

			<div class="col-md-4">
				<div class="list-port">
				  <iframe src="https://drive.google.com/file/d/1bToH4PgOOLRisySqVOWRrz8PHFkl7YlJ/preview"></iframe>
				</div>
			</div>

			<div class="col-md-4">
				<div class="list-port">
				  <iframe src="https://drive.google.com/file/d/1lLTRVeA4Lu0JygRHw8w66jxWmd5BQvSc/preview"></iframe>
				</div>
			</div>
		  {:else}
		  {/if}
	  </div>
     
	  <Footer />
	  
	</div>
	{:catch error}
      <p>Error fetch JSON data!</p>
	{/await}