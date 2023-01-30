<script>
	import Header from '../components/UI/Header/Header.svelte';
	import '../app.css';
</script>

<Header />
<main class="main__app">
	<slot />
</main>

<style>
	.main__app {
		/* margin-top: 5rem; */
		max-width: 1200px;
		padding-top: 5rem;
		margin: 0 auto 0 auto;
	}

	form {
		width: 30rem;
	}
</style>
