<script>
	export let number = 0;
	export let title = '';
	export let subtitle = '';
</script>

<div class="total-loss-card">
	<div class="title">{title}</div>

	<div class="right">
		<div class="number">{number}</div>
		<div class="subtitle">{subtitle}</div>
	</div>
</div>

<style lang="scss">
	.total-loss-card {
		display: flex;
		align-items: center;
		gap: 8px;
		width: fit-content;
		padding: 0;
		background-color: transparent;
	}

	.right {
		display: flex;
		align-items: center;
		gap: 8px;
		width: fit-content;
		height: fit-content;
	}

	.number {
		font-size: 32px;
		font-weight: 700;
		color: red;
	}

	.title {
		font-size: 13px;
		font-weight: 700;
	}

	.subtitle {
		font-size: 13px;
		font-weight: 700;
	}
</style>
