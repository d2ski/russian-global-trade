<script>
	export let checked;
	export let label;
</script>

<label class="container">
	<input type="checkbox" bind:checked />
	<span class="checkmark" />
	{label}
</label>

<style>
	/* Customize the label (the container) */
	.container {
		display: inline-block;
		position: relative;
		padding-left: 1.7rem;
		/* margin-left: 1rem; */
		cursor: pointer;
		font-size: 0.9rem;
		line-height: 1.375rem;
		-webkit-user-select: none;
		-moz-user-select: none;
		-ms-user-select: none;
		user-select: none;
	}

	/* Hide the browser's default checkbox */
	.container input {
		position: absolute;
		opacity: 0;
		cursor: pointer;
		height: 0;
		width: 0;
	}

	/* Create a custom checkbox */
	.checkmark {
		position: absolute;
		top: 0;
		left: 0;
		height: 1.35rem;
		width: 1.35rem;
		background-color: var(--color-dark-light);
	}

	/* On mouse-over, add a grey background color */
	.container:hover input ~ .checkmark {
		background-color: var(--color-dark-medium);
	}

	/* When the checkbox is checked, add a blue background */
	.container input:checked ~ .checkmark {
		background-color: var(--color-dark-primary);
	}

	/* Create the checkmark/indicator (hidden when not checked) */
	.checkmark:after {
		content: '';
		position: absolute;
		display: none;
	}

	/* Show the checkmark when checked */
	.container input:checked ~ .checkmark:after {
		display: block;
	}

	/* Style the checkmark/indicator */
	.container .checkmark:after {
		left: 0.45rem;
		top: 0.2rem;
		width: 0.3rem;
		height: 0.6rem;
		border: solid white;
		border-width: 0 2px 3px 0;
		-webkit-transform: rotate(45deg);
		-ms-transform: rotate(45deg);
		transform: rotate(45deg);
	}
</style>
