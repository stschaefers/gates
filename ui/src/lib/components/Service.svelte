<script lang="ts">
	import Gate from './Gate.svelte';
	import type { Service } from '$lib/api';

	export let service: Service;
</script>

<div class="w-full">
	<div
		class="gate-service grid md:grid-cols-{service.environments
			.length} space-y-5 md:space-y-0 md:space-x-5"
	>
		{#each service.environments as environment (environment.name)}
			<Gate gate={environment.gate} />
		{/each}
	</div>
</div>
