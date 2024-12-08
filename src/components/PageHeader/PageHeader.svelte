<script>
	import { Button } from 'kiwi-nl';
</script>

<div class="page-header">
	<h2>What's The Cost?</h2>
	<div class="buttons">
		<Button type="secondary" href="https://www.ncpgambling.org/help-treatment/" target="_blank">
			<div>Get Help</div>
		</Button>
		<Button>
			<div>Add Betting App</div>
		</Button>
	</div>
</div>

<style lang="scss">
	@import '../../variables.css';
	.page-header {
		margin: 16px 256px;
		border-radius: 16px;
		display: flex;
		align-items: center;
		justify-content: space-between;
		color: var(--text-color);
		padding: 0 16px;
		user-select: none;
	}

	.buttons {
		display: flex;
		gap: 16px;
	}
</style>
