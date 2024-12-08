<script>
	import BettingAppLogo from '../components/BettingAppLogo/BettingAppLogo.svelte';
	import BetsPlacedCard from '../components/BetsPlacedCard/BetsPlacedCard.svelte';
	import ImpactCard from '../components/ImpactCard/ImpactCard.svelte';
	import TimeFrameSelector from '../components/TimeFrameSelector/TimeFrameSelector.svelte';
	import TotalLossCard from '../TotalLossCard/TotalLossCard.svelte';
	import Chart from '../components/Chart/Chart.svelte';
	import ComparisonText from '../components/ComparisonText/ComparisonText.svelte';
</script>

<div class="page">
	<div class="section">
		<div class="section-header">
			<h2>Within</h2>
			<TimeFrameSelector selectedTimeFrame="This Week" />
		</div>
		<div class="impact-subheader">
			<h3>Here is the impact you have made in your life</h3>
		</div>
		<div class="cards">
			<ImpactCard number="25" title="Bets Placed" subtitle="Across 3 Apps">
				<div class="impactcard1">
					<BettingAppLogo />
					<BettingAppLogo name="Bet365" />
					<BettingAppLogo name="BetMGM" />
				</div>
			</ImpactCard>
			<ImpactCard number="20" title="Bets Lost" subtitle="Of Bets Placed">
				<div class="impactcard2">80%</div>
			</ImpactCard>
			<ImpactCard number="$850" title="Placed On Bets" subtitle="Up From Last Week">
				<div class="impactcard3">
					<svg
						width="13"
						height="9"
						viewBox="0 0 13 9"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M11.0433 8.95866H2.62332C2.29091 8.95914 1.96516 8.86547 1.68377 8.6885C1.40238 8.51153 1.17686 8.25848 1.03332 7.95866C0.865288 7.60292 0.800569 7.20713 0.846538 6.81639C0.892507 6.42565 1.04732 6.05569 1.29332 5.74866L5.50332 0.648659C5.66854 0.458029 5.8728 0.305143 6.10227 0.200361C6.33174 0.0955797 6.58106 0.0413513 6.83332 0.0413513C7.08558 0.0413513 7.3349 0.0955797 7.56437 0.200361C7.79384 0.305143 7.9981 0.458029 8.16332 0.648659L12.3733 5.74866C12.6193 6.05569 12.7741 6.42565 12.8201 6.81639C12.8661 7.20713 12.8014 7.60292 12.6333 7.95866C12.4898 8.25848 12.2643 8.51153 11.9829 8.6885C11.7015 8.86547 11.3757 8.95914 11.0433 8.95866Z"
							fill="#FF0000"
						/>
					</svg>
					$250
				</div>
			</ImpactCard>
			<ImpactCard number="$600" title="Lost On Bets" subtitle="Of Money Wagered">
				<div class="impactcard2">%70</div>
			</ImpactCard>
		</div>
	</div>
	<div class="section">
		<div class="section-header">
			<h2>In Total You Have</h2>
		</div>
		<div class="cards">
			<TotalLossCard number="276" title="Gambled Your Hard Earned Money" subtitle="Times" />
			<TotalLossCard number="3500" title="Given The Sports Betting Companies" subtitle="Dollars" />
		</div>
		<Chart />
	</div>
	<div class="section">
		<div class="section-header">
			<h2>
				With the <strong>$3500</strong> you lost, here are some things you could have used it for
			</h2>
		</div>
		<div class="comparisons">
			<ComparisonText start="Bought " middle="700 Cups" end=" of Coffee" />
			<ComparisonText start="Paid " middle="3 Months" end=" of Rent" />
			<ComparisonText start="Provided Yourself Food For " middle=" 22.4 Weeks" />
			<ComparisonText start="Purchased " middle="14 Shares" end=" of Apple Stock" />
			<ComparisonText start="Protected " middle="500 Children" end=" from Malaria" />
			<ComparisonText start="Nourished Starving Children With " middle=" 12,068 Meals" />
		</div>
		<Chart />
	</div>
</div>

<style lang="scss">
	@import '../variables.css';

	.page {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width: 100%;
		gap: 64px;
	}

	.section {
		display: flex;
		flex-direction: column;
		align-items: start;
		justify-content: start;
		width: 100%;
		gap: 8px;
	}

	.section-header {
		display: flex;
		align-items: center;
		gap: 16px;
		width: 100%;
	}

	.impactcard1 {
		display: flex;
		width: fit-content;
		gap: 10px;
	}

	.impactcard2 {
		font-size: 24px;
		color: red;
		font-weight: 700;
	}

	.impactcard3 {
		display: flex;
		align-items: center;
		gap: 4px;
		font-size: 24px;
		color: red;
		font-weight: 700;
	}

	.cards {
		display: flex;
		align-items: center;
		justify-content: space-between;
		width: 100%;
	}

	h2 {
		margin: 0;
		padding: 0;
	}

	h3 {
		margin: 0;
		padding: 0;
	}

	strong {
		color: red;
		font-weight: 600;
	}
</style>
