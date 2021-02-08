<script lang="ts">
import Input from './Input.svelte'

export let name = "Japan"
let email = 'hoge@hoge.com'
let placeholder = 'hogehoge'

const callbackFunctionFromInput = (event) => {
	console.log(event.detail)
	name = event.detail
}

</script>

<main>
	<h1>Hello {name}!</h1>
	<p>{email}</p>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<Input {placeholder} on:emitAddText={callbackFunctionFromInput} />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>