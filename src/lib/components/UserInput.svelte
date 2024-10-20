<script lang="ts">
	import type { Snippet } from 'svelte';

	interface UserInputInterface {
		children: Snippet;
		userName: string;
	}
	let { userName, children, ...props }: UserInputInterface = $props();
	// $inspect(children, 'data');
</script>

<h1>Your username is: {userName}</h1>
<input type="text" bind:value={userName} placeholder="Your Username" />
{@render children()}

<p></p>

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
</style>
