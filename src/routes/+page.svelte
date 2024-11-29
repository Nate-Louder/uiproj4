<script>
	import BettingAppLogo from '../components/BettingAppLogo/BettingAppLogo.svelte';
	import BetsPlacedCard from '../components/BetsPlacedCard/BetsPlacedCard.svelte';
</script>

<div class="page">
	HI
	<BettingAppLogo />
	<BettingAppLogo name="BetMGM" />
	<BetsPlacedCard betAmount={5} />
</div>

<style lang="scss">
	@import '../variables.css';

	.page {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
</style>
