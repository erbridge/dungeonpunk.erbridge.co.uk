<script lang="ts">
	export let name: string;
	export let replace = false;
</script>

<section>
	<h3 data-replace={replace}>
		basic move: {name}
		{#if replace}<span>(replaces original)</span>{/if}
	</h3>
	<slot />
</section>

<style>
	section {
		break-inside: avoid;
	}

	h3[data-replace] {
		margin-bottom: 0;
	}

	h3 > span {
		vertical-align: middle;
		font-size: 0.7em;
		font-weight: normal;
		font-style: italic;
	}
</style>
