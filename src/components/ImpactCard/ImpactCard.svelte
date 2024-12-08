<script>
	export let number = 0;
	export let title = '';
	export let subtitle = '';
</script>

<div class="impact-card">
	<div class="left">
		<div class="number">{number}</div>
		<div class="title">{title}</div>
	</div>
	<div class="line"></div>
	<div class="right">
		<div class="subtitle">{subtitle}</div>
		<div clas="metadata">
			<slot></slot>
		</div>
	</div>
</div>

<style lang="scss">
	@import '../../variables.css';

	.impact-card {
		display: flex;
		align-items: center;
		justify-content: space-between;
		width: fit-content;
		gap: 16px;
		padding: 0;
		background-color: transparent;
	}

	.line {
		width: 1px;
		height: 50px;
		background-color: white;
	}

	.left {
		display: flex;
		flex-direction: column;
		align-items: center;
		width: fit-content;
		height: fit-content;
	}

	.right {
		display: flex;
		align-items: center;
		flex-direction: column;
		gap: 10px;
		width: fit-content;
		height: fit-content;
	}

	.number {
		font-size: 32px;
		font-weight: 700;
	}

	.title {
		font-size: 13px;
		font-weight: 700;
	}

	.subtitle {
		font-size: 11px;
		font-weight: 700;
	}

	.metadata {
		font-size: 14px;
		font-weight: 400;
		color: var(--text-color-light);
	}
</style>
