<script lang="ts">
import { createEventDispatcher } from "svelte";

export let placeholder = 'hoge'

export let value = ''

const dispatch = createEventDispatcher()

const addText = () => {
    console.log('click')
    dispatch('emitAddText', value)
}

const sendMessage = () => {
    console.log('send message')
}
</script>
<div>
    <input placeholder={placeholder} bind:value={value} />
</div>
<button on:click={addText} on:click={sendMessage}>add</button>
