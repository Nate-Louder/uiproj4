<script>
	import PageHeader from '../components/PageHeader/PageHeader.svelte';
</script>

<div class="app">
	<div class="app__header">
		<PageHeader />
	</div>
	<div class="app__content">
		<div class="stuff">
			<slot></slot>
		</div>
	</div>
</div>

<style lang="scss">
	/* Add global styles here */
	@import '../variables.css';

	.app {
		padding: 0;
		margin: 0;
		color: var(--text-color);
		height: 100vh;
		overflow: hidden;
	}

	.app__content {
		overflow-y: auto;
		height: 100%;
	}

	.stuff {
		display: flex;
		justify-content: center;
		max-width: 1000px;
		margin: 24px auto;
	}
</style>
