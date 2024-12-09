<script>
	import { Button } from 'kiwi-nl';
	let { showModal = $bindable(), header, children } = $props();

	let dialog = $state();

	$effect(() => {
		if (showModal) dialog.showModal();
	});
</script>

<!-- svelte-ignore a11y_click_events_have_key_events, a11y_no_noninteractive_element_interactions -->
<dialog
	bind:this={dialog}
	onclose={() => (showModal = false)}
	onclick={(e) => {
		if (e.target === dialog) dialog.close();
	}}
>
	<div class="stuff">
		{@render children?.()}
		<div class="buttons">
			<Button type="tertiary" on:click={() => dialog.close()}>Close</Button>
			<Button on:click={() => dialog.close()}>Save</Button>
		</div>
	</div>
</dialog>

<style>
	dialog {
		max-width: 32em;
		border-radius: 0.2em;
		border: none;
		padding: 0;
		background-color: black;
	}
	dialog::backdrop {
		background: rgba(0, 0, 0, 0.3);
	}
	dialog > div {
		padding: 1em;
	}
	dialog[open] {
		animation: zoom 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
	}
	@keyframes zoom {
		from {
			transform: scale(0.95);
		}
		to {
			transform: scale(1);
		}
	}
	dialog[open]::backdrop {
		animation: fade 0.2s ease-out;
	}
	@keyframes fade {
		from {
			opacity: 0;
		}
		to {
			opacity: 1;
		}
	}

	.stuff {
		display: flex;
		flex-direction: column;
		gap: 16px;
	}

	.buttons {
		display: flex;
		gap: 16px;
		width: 100%;
		justify-content: space-between;
	}
</style>
