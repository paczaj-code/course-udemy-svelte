<script>
	// @ts-nocheck
	import Product from './Product.svelte';

	function addToCart(event) {
		console.log(event.detail);
	}

	function deleteProduct(event) {
		console.log(event.detail);
	}

	const product = {
		productTitle: 'A book',
		id: '33'
	};
</script>

<Product {...product} on:add-to-cart={addToCart} on:delete={deleteProduct} />
