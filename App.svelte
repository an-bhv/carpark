<script>
	import Home from "./Home.svelte"; 
	import Signup from "./Signup.svelte";
	import Otp from "./Otp.svelte";
	import {Router, Route} from "svelte-navigator";
</script>

<Router>
<main>
	<!--<Home />-->
	<Route path = "/"><Home /></Route>
	<Route path = "/Signup"><Signup /></Route>
	<Route path = "/Otp"><Otp /></Route>
</main>
</Router>
	
<style>
	
	main{
		display: flex;
		flex-direction: column;
	}

	/*h1{
		font-size: 72px;
		text-align: center;
	}

	h3{
		font-size: 38px;
	}*/
</style>