<script>
	import TimeFrameSelector from '../TimeFrameSelector/TimeFrameSelector.svelte';
	import BettingAppLogo from '../BettingAppLogo/BettingAppLogo.svelte';

	export let betAmount = 0;
	export let appNames = ['FanDuel', 'DraftKings', 'BetMGM'];
	export let timeFrame = 'Today';
</script>

<div class="bets-placed-card">
	<div class="bets-placed-card__upper">
		<div class="bets-placed-card__amount">
			<div class="amount">
				{betAmount}
			</div>
			<div class="bets-placed">Bets Placed</div>
		</div>
		<div class="bets-placed-card__time-frame">
			<TimeFrameSelector selectedTimeFrame={timeFrame} />
		</div>
	</div>
	<div class="bets-placed-card__lower">
		<div class="bets-placed-card__app-amount">
			In {appNames.length} Apps
		</div>
		<div class="bets-placed-card__app-names">
			{#each appNames as appName}
				<BettingAppLogo name={appName} />
			{/each}
		</div>
	</div>
</div>

<style lang="scss">
	@import '../../variables.css';

	.bets-placed-card {
		width: 315px;
		height: fit-content;
		border-radius: 8px;
		background-color: var(--surface-light-color);
		padding: 8px;
		display: flex;
		flex-direction: column;
		gap: 8px;
	}

	.bets-placed-card__upper {
		display: flex;
		justify-content: space-between;
	}

	.bets-placed-card__amount {
		display: flex;
		flex-direction: column;
		gap: 4px;
	}

	.amount {
		font-size: 32px;
		font-weight: 700;
	}

	.bets-placed {
		font-size: 13px;
		font-weight: 600;
	}

	.bets-placed-card__lower {
		display: flex;
		flex-direction: column;
		gap: 10px;
	}

	.bets-placed-card__app-amount {
		font-size: 11px;
		font-weight: 500;
		color: #dfdfdf;
	}

	.bets-placed-card__app-names {
		display: flex;
		gap: 10px;
	}
</style>
