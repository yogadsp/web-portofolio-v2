<script>
	import { Router, Route, Link } from "svelte-routing";
  import Home from "./pages/Home.svelte";
  import Portfolio from "./pages/Portfolio.svelte";
  import Others from "./pages/Others.svelte";
  import Detail from './pages/Detail.svelte';
</script>

<!-- navigation menu custom -->
<Router>
 <nav class="nav lato-font justify-content-center">
    <a class="nav-link" href="/">home</a>
    <a class="nav-link" href="/portfolio">portfolio</a>
    <a class="nav-link" href="/others">others</a>
  </nav>
  <div>
  	<Route path="/" component="{Home}" /> 
    <Route path="/portfolio" component="{Portfolio}" /> 
    <Route path="/others" component="{Others}" /> 
    <Route path="portfolio/detail" component="{Detail}" />
  </div>
</Router>