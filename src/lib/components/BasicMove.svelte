<script lang="ts">
	export let name: string;
	export let replace = false;
</script>

<section>
	<h3 data-replace={replace}>
		basic move: {name}
		{#if replace}<span>(replaces original)</span>{/if}
	</h3>
	{#if replace}<span>(replaces original)</span>{/if}
	<slot />
</section>

<style>
	h3[data-replace] {
		margin-bottom: 0;
	}

	h3 + span {
		margin-top: 0;
		font-size: 0.9em;
		font-style: italic;
	}
</style>
