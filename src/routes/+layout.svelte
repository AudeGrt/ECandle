<script lang="ts">
	import '../app.css';
	let { children } = $props();
	import { page} from '$app/state';
	import CartPopover from '$lib/components/CartPopover.svelte';

	const navPage= [{
		name:"Home",
		path:"/"
	},{
		name:"Produits",
		path:"/products"
	},{
		name:"Qui sommes-nous ?",
		path:"/aboutUs"
	},{
		name:"Contact",
		path:"/contact"
	}]
</script>

<nav class="mb-6 bg-transparent py-4 absolute w-full px-6">
	<div class="container mx-auto flex items-center justify-around  text-white text-xl ml-3">
		<div class="w-3/4 flex gap-20">
			{#each navPage as navButton}
			<a href={navButton.path} class='hover:font-bold {page.url.pathname===navButton.path?"border-b-1 hover:border-b-2":""}'>{navButton.name}</a>
			{/each}
		</div>
			<div class="w-1/4 flex justify-end">
				<CartPopover />
			</div>
	</div>
</nav>

<main class="container mx-auto h-full text-white p-12">
	<div class="mt-12">
		{@render children()}
	</div>
</main>

