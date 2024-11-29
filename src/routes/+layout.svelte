<script>
	import PageHeader from '../components/PageHeader/PageHeader.svelte';
</script>

<div class="app">
	<div class="app__header">
		<PageHeader />
	</div>
	<div class="app__content">
		<slot></slot>
	</div>
</div>

<style lang="scss">
	/* Add global styles here */
	@import '../variables.css';

	.app {
		height: 100%;
		padding: 0;
		margin: 0;
		color: var(--text-color);
	}

	.app__content {
		display: flex;
		justify-content: center;
		max-width: 1000px;
		margin: 24px auto;
		color: var(--text-color);
	}
</style>
