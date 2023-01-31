<script>
	import { createEventDispatcher } from 'svelte';
	import Button from '../../components/UI/Button/Button.svelte';
	import Modal from './Modal.svelte';
	export let productTitle = '';
	export let id = '';

	let showModal = false;

	const dispatch = createEventDispatcher();

	function addToCart() {
		dispatch('add-to-cart', { dupa: true });
	}

	function deleteProduct() {
		dispatch('delete', { dupa: false });
	}

	$: console.log(showModal);
</script>

<article>
	<h1>{productTitle}</h1>
	<p>{id}</p>
	<button on:click={addToCart}>Add to cart</button>
	<button on:click={deleteProduct}>Delete</button>
</article>

<!-- <button on:click={() => (showModal = !showModal)} > -->
<button on:click={() => (showModal = !showModal)}>Show modal</button>
<!-- <Modal>
	<h2 style="background: gray;" slot="modal-header">Modal</h2>
	<p slot="modal-content">Works!!!!</p>
	<Button caption="Dupa" slot="modal-footer" />
</Modal> -->
