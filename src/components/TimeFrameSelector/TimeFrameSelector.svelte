<script>
	import { Popover, PopoverTrigger, PopoverContent, Button } from 'kiwi-nl';
	import { createEventDispatcher } from 'svelte';

	export let selectedTimeFrame = 'Today';
	$: selectedTimeFrame;

	let popoverElement;
	let selectableTimeFrames = ['Today', 'This Week', 'This Month'];

	let dispatch = createEventDispatcher();

	function handleClick() {
		if (popoverElement) {
			popoverElement.close();
		}
	}
</script>

<Popover bind:this={popoverElement}>
	<PopoverTrigger slot="trigger" fullwidth={false} fullheight={false}>
		<div slot="custom-trigger" class="trigger">{selectedTimeFrame}</div>
	</PopoverTrigger>
	<PopoverContent slot="content">
		<div class="header-dropdown-timeframes" slot="custom-content">
			{#each selectableTimeFrames as timeFrame}
				<!-- svelte-ignore a11y_click_events_have_key_events -->
				<!-- svelte-ignore a11y_no_static_element_interactions -->
				<div
					class="timeframe"
					on:click={() => {
						selectedTimeFrame = timeFrame;
						popoverElement.close();
						dispatch('timeFrameSelected', timeFrame);
					}}
				>
					{timeFrame}
				</div>
			{/each}
		</div>
	</PopoverContent>
</Popover>

<style>
	@import '../../variables.css';
	.header-dropdown-timeframes {
		display: flex;
		width: fit-content;
		flex-direction: column;
		gap: 8px;
	}

	.timeframe {
		white-space: nowrap;
		border-radius: 4px;
		padding: 2px 8px;
		cursor: pointer;
		user-select: none;
		color: var(--surface-light-color);
	}

	.timeframe:hover {
		background-color: #83f1e250;
	}

	.trigger {
		width: 100px;
		height: 24px;
		border-radius: 8px;
		background-color: transparent;
		color: var(--color-primary);
		border: 1px solid var(--color-primary);
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.trigger:hover {
		background-color: #83f1e250;
	}
</style>
