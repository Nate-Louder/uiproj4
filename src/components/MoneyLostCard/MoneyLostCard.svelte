<script>
	import TimeFrameSelector from '../TimeFrameSelector/TimeFrameSelector.svelte';
	import BettingAppLogo from '../BettingAppLogo/BettingAppLogo.svelte';
	import { data } from '../../data.js';

	let timeFrame = 'This Month';
	let numberOfBets = 0;
	let apps = new Set();

	const handleTimeFrameChanged = (event) => {
		timeFrame = event.detail;
		({ numberOfBets, apps } = parseData());
	};

	const parseData = () => {
		let numberOfBets = 0;
		let apps = new Set();
		let today = new Date();
		let timeFrameEnd = new Date();

		if (timeFrame === 'This Week') {
			timeFrameEnd.setDate(today.getDate() - 7);
		} else if (timeFrame === 'This Month') {
			timeFrameEnd.setDate(today.getDate() - 30);
		} else {
			timeFrameEnd = today;
		}

		data.userBets.forEach((bet) => {
			let betDate = new Date(bet.date);
			if (betDate >= timeFrameEnd && betDate <= today) {
				numberOfBets++;
				apps.add(data.userBettingApps.find((app) => app.id === bet.appId)).name;
			}
		});

		return {
			numberOfBets,
			apps: Array.from(apps)
		};
	};

	({ numberOfBets, apps } = parseData());
</script>

<div class="bets-placed-card">
	<div class="bets-placed-card__upper">
		<div class="bets-placed-card__amount">
			<div class="amount">
				{numberOfBets}
			</div>
			<div class="bets-placed">Bets Placed</div>
		</div>
		<div class="bets-placed-card__time-frame">
			<TimeFrameSelector
				selectedTimeFrame={timeFrame}
				on:timeFrameSelected={handleTimeFrameChanged}
			/>
		</div>
	</div>
	<div class="bets-placed-card__lower">
		<div class="bets-placed-card__app-amount">
			In {apps.length} Apps
		</div>
		<div class="bets-placed-card__app-names">
			{#each apps as app}
				<BettingAppLogo name={app.name} />
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
