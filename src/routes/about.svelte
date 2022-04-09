<script lang="ts" context="module">
	import type { Load } from '@sveltejs/kit';

	// A dummy load function that takes a while to complete
	export const load: Load = async () => {
		return new Promise((resolve) => {
			const res = () =>
				resolve({
					status: 200
				});
			setTimeout(res, 1000);
		});
	};
</script>

<h1>About Page</h1>

<a href="/">Back Home</a>
