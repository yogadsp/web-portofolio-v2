<script>
  import { fade } from 'svelte/transition';
  let pageName="Others";
</script>

<!-- change title bar name with svelte special tags -->
<svelte:head>
    <title>Yoga Dwi Septana | {pageName}</title>
</svelte:head>

<div style="margin-bottom: 2%;"></div>
    
<div class="container" transition:fade="{{duration: 450}}">
  <div class="row">
    <div class="col-md-12 home-content">
      <h1 class="title-font">Others</h1>
      <div style="margin-bottom: 4%;"></div>
    </div>
  </div>
  <div class="row port-container">
    <div class="col-md-12">
        <div class="list-port desc-font">
          <div class="desc-port">
            <b>Coming Soon!</b>
          </div>
        </div>
    </div>
    
  </div>
</div>