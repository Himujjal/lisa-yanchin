<script>
	import Iconify from '@iconify/svelte';
	import '../app.postcss';

	let openDrawer = false;
</script>

{#if openDrawer}
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<!-- svelte-ignore a11y-no-static-element-interactions -->
	<div
		class="z-[9] bg-gray-500 opacity-50 fixed top-0 left-0 w-full h-full transition-all"
		on:click={() => (openDrawer = false)}
	/>
{/if}

<div
	class="w-1/2 bg-white h-full fixed top-0 z-10 transition-all {openDrawer
		? 'left-0'
		: 'left-[-50%]'} flex flex-col justify-between"
>
	<div class="text-end p-4 text-gray-400">
		<button on:click={() => (openDrawer = false)}>Back <span class="text-red-400">→</span></button>
	</div>

	<div class="p-4">
		<div class="border-top p-2 flex justify-center items-center">
			<Iconify icon="mdi:heart" color="red" />
			<span>Favourites</span>
		</div>
		<div class="border-top p-2 flex justify-center items-center">
			<Iconify icon="mdi:account-circle" color="red" />
			<span>Profile</span>
		</div>
		<div class="border-top p-2 flex justify-center items-center">
			<Iconify icon="mdi:help-circle" color="red" />
			<span>Help</span>
		</div>
		<div class="w-full flex justify-between items-center bg-red-100">
			<span class="p-2">Yanchin</span>
			<img src="/yanchin-favicon.jpeg" alt="Y" />
		</div>
	</div>
</div>

<nav class="h-24 md:h-16 md:flex fixed top-0 left-0 w-full">
	<div class="w-full md:w-2/3 h-18 flex justify-around items-center p-2">
		<span class="px-4">
			<select placeholder="Location">
				<option disabled selected value>-- Location --</option>
				<option>Jayanagar</option>
				<option disabled>Jagiroad (Coming soon)</option>
			</select>
		</span>
		<a class="h-12 overflow-hidden" href="/">
			<img class="" src="/yanchin-logo.jpg" alt="Yanchin" />
		</a>
	</div>
	<div class="h-6 md:h-16 flex justify-center items-center w-full md:w-1/3">
		<span class="w-full justify-center flex">
			<input type="search" class="w-[80%] bg-[#D5D5D5]" />
			<span class="flex justify-center items-center bg-[#D5D5D5] p-2">
				<Iconify icon="mdi:search" />
			</span>
		</span>
	</div>
</nav>

<div class="h-24" />

<slot />

<div class="h-12" />

<div class="h-12 fixed bottom-0 left-0 w-full flex justify-around bg-[#F80200] items-center">
	<button on:click={() => (openDrawer = true)}>
		<Iconify icon="mingcute:dot-grid-fill" width="24" height="24" />
	</button>

	<button>
		<Iconify icon="mingcute:fork-spoon-fill" width="24" height="24" />
	</button>

	<button>
		<Iconify icon="mingcute:shopping-cart-2-fill" width="24" height="24" />
	</button>
</div>

<style>
	.border-top {
		border-top: 1px solid #d5d5d5;
	}
	.border-top:hover {
		border-top: 1px solid red;
	}
</style>
