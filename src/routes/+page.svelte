<script lang="ts">
	import { sound } from 'svelte-sound';
	import click_sound from '$lib/assets/mixkit-hard-typewriter-click-1119.wav';
	import hover_sound from '$lib/assets/mixkit-helicopter-flying-far-away-2715.wav';
	import UserInput from '$lib/components/UserInput.svelte';

	let number = $state(0);
</script>

<UserInput userName = "">
    <h1>Dette er en test af component destructuring of props</h1>
</UserInput>
<!-- <UserInput /> -->

<button
    use:sound={{
        src: hover_sound,
        events: ['mouseover', 'mouseout'],
        loop: true
    }}
	use:sound={{
		src: click_sound,
		events: ['click']
	}}
	onclick={() => number++}>Click me!</button
>

<style>
	* {
		font-size: 2rem;
		display: flex;
		justify-content: center;
		/* text-align: center;
        align-items: center;
        align-content: center; */
		margin: auto;
		padding: 20px;
	}
	button {
		padding: 4px;
		border-radius: 8px;
		border-width: 4px;
		border-color: red;
	}
</style>
