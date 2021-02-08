<script lang="ts">
	import Router, {link} from 'svelte-spa-router'
	import Home from './Home.svelte'
	import About from './About.svelte'
	import List from './List.svelte'

	const name = 'world'

    const routes = {
	  '/': Home,
	  '/about': About,
	  '/list': List,
	  '*': Home
	}
</script>

<main>
	<div class="main__content--wrapper">
		<nav class="main__navbar--wrapper">
			<ul>
				<li><a href="/" use:link>home</a></li>
				<li><a href="/about" use:link>about</a></li>
				<li><a href="/list" use:link>list</a></li>
			</ul>
		</nav>
		<Router {routes}></Router>
	</div>
</main>

<style>
	main {
		text-align: center;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
	.main__content--wrapper {
		display:flex
	}
	.main__navbar--wrapper {
		width: 150px;
		color: white;
		background-color: darkolivegreen;
		height: 100vh;
		text-align: left;
		line-height: 2em;
	}
	ul {
		list-style: none;
	}
	ul  a {
		color: white;
	}
</style>