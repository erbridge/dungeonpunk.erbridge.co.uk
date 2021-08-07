<ul>
	{#if $$slots.success}<li>On a <strong>success</strong>: <slot name="success" /></li>{/if}
	{#if $$slots.twist}<li>On a <strong>twist</strong>: <slot name="twist" /></li>{/if}
	{#if $$slots.failure}<li>On a <strong>failure</strong>: <slot name="failure" /></li>{/if}
</ul>

<style>
	ul {
		margin-top: -1em;
	}

	li::before {
		content: '';
		margin: 0;
	}
</style>
