<script>
	import { Button, TextInput } from 'kiwi-nl';
	import Modal from '../Modal/Modal.svelte';

	let showModal = $state(false);
</script>

<div class="page-header">
	<h2>What's The Cost?</h2>
	<div class="buttons">
		<Button type="secondary" href="https://www.ncpgambling.org/help-treatment/" target="_blank">
			<div>Get Help</div>
		</Button>
		<Button on:click={() => (showModal = true)}>
			<div>Add Betting App</div>
		</Button>
	</div>
	<Modal bind:showModal>
		<h2>Add A Betting App</h2>
		<div class="modal-contents">
			<TextInput label="App URL" />
			<TextInput label="App Username" />
			<TextInput label="App Password" />
		</div>
	</Modal>
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

	h2 {
		color: white;
	}

	.modal-contents {
		display: flex;
		flex-direction: column;
		gap: 16px;
	}

	.buttons {
		display: flex;
		gap: 16px;
	}
</style>
