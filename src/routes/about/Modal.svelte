<script>
	import Button from '../../components/UI/Button/Button.svelte';
	import Header from '../../components/UI/Header/Header.svelte';

	// export let content = '';
</script>

<div class="backdrop" />
<div class="modal">
	<header><slot name="modal-header" /></header>
	<div class="content"><slot name="modal-content" /></div>
	<footer>
		<slot name="modal-footer">
			<Button caption="close" />
		</slot>
	</footer>
</div>

<style>
	.backdrop {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100vh;
		background: rgba(0, 0, 0, 0.75);
		z-index: 10;
	}

	.modal {
		padding: 1rem;
		position: fixed;
		top: 10vh;
		left: 10%;
		width: 80%;
		max-height: 80vh;
		background: white;
		border-radius: 5px;
		z-index: 100;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
		overflow: hidden;
	}
</style>
