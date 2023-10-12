<script lang="ts">
	import { page } from '$app/stores';

	const {
		params: { id }
	} = $page;
</script>

<div class="m-8">
	<h1 class="my-8 text-2xl capitalize">{id}</h1>
	{#each [0, 1, 2] as i}
		<div class="flex">
			<img src={`/${id}.jpeg`} alt="{id}-{i}" />
			<div class="m-2">
				<div>
					Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
					ut labore et dolore magna aliqua.
				</div>
				<div class="flex justify-between my-4">
					<span class="italic">Ingredients: --</span>
					<button class="bg-red-600 text-white px-4">Add</button>
				</div>
				<div class="text-xs flex justify-end text-red-400 mt-4">Add cooking instructions</div>
			</div>
		</div>
		<hr class="m-2" />
	{/each}
</div>
