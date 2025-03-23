<script lang="ts">
	let categoryCard = [
		{ title: 'Best Sellers', img: '/images/bestSellers.jpg', isNew: false, description:"Découvrez nos bests sellers du moment !", path:"/products"},
		{ title: 'Nouveautés', img: '/images/news.jpg', isNew: true , description:"Découvrez nos nouveautés du moment !", path:"/products"},
		{ title: 'Tout les produits', img: '/images/allProducts.jpg', isNew: false , description:"Découvrez notre gamme de produit complète !", path:"/products"}
	];
</script>

<header class="my-20 text-center">
	<h1 class="mb-4 text-4xl font-extrabold">Bienvenue dans notre boutique de bougies</h1>
	<p class="text-lg text-white">
		Découvrez nos bougies artisanales parfumées pour chaque moment spécial
	</p>
</header>

<div class="flex justify-around gap-18 h-[500px]">
	{#each categoryCard as category}
		<div class="h-full w-full flex flex-col items-center">
			<h1 class="mb-4 text-2xl text-black">{category.title}</h1>
			<div class="overflow-hidden rounded-3xl product-card">
				<div class="relative">
					<img src={category.img} alt={category.title} class="object-cover image-container" />
					{#if category.isNew}
						<span
							class="absolute top-4 right-4 rounded-full bg-white px-4 py-1 text-sm font-semibold text-amber-700 shadow-lg"
						>
							New
						</span>
					{/if}
					<div class="overlay">
						{category.description}
					</div>
				</div>
			</div>
		</div>
	{/each}
</div>

<style>

    .product-card {
        position: relative;
        overflow: hidden;
        border-radius: 1rem;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .product-card:hover {
        transform: scale(1.05);
        box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
    }

    .image-container {
        position: relative;
        overflow: hidden;
    }

    .overlay {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background: rgba(0, 0, 0, 0.6);
        color: white;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        opacity: 0;
        transition: opacity 0.3s ease;
    }

    .product-card:hover .overlay {
        opacity: 1;
    }
</style>