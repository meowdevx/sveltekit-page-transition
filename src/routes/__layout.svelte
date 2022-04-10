<script lang="ts">
	import { afterNavigate, beforeNavigate } from '$app/navigation';
	import { fade } from 'svelte/transition';
	import Loading from '$lib/components/Loading.svelte';

	$: loading = false;

	beforeNavigate(() => {
		loading = true;
	});

	afterNavigate(() => {
		loading = false;
	});
</script>

<div class="wrapper">
	{#if loading}
		<div class="modal" in:fade out:fade>
			<Loading />
		</div>
	{/if}
	<slot />
</div>

<style>
	.modal {
		display: grid;
		place-items: center;
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		background-color: rgba(26, 18, 25, 0.63);
		backdrop-filter: blur;
	}
</style>
