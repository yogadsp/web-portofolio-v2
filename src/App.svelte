<script>
	import { Router, Route, Link } from "svelte-routing";
  import Home from "./pages/Home.svelte";
  import Portfolio from "./pages/Portfolio.svelte";
  import Others from "./pages/Others.svelte";
  //import DetailPortfolio from './pages/DetailPortfolio.svelte'; //test page
  import Detail from './pages/Detail.svelte';
</script>

<!-- navigation menu custom -->
<Router>
 <nav class="nav lato-font justify-content-center">
    <Link to="/">home</Link>
    <Link to="portfolio">portfolio</Link>
    <Link to="others">others</Link>
    <!-- <Link to="detaill">detail</Link> --> <!-- test page -->
  </nav>
  <div>
  	<Route path="/" component="{Home}" /> 
    <Route path="portfolio" component="{Portfolio}" /> 
    <Route path="others" component="{Others}" /> 
    <Route path="portfolio/detail" component="{Detail}" />
    <!-- <Route path="detaill" component="{DetailPortfolio}" /> --> <!-- test page -->
  </div>
</Router>