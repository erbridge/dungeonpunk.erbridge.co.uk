<script lang="ts">
	import "normalize.css";
</script>

<svelte:head>
	<meta name="theme-color" content="#f8ede5" />

	<style>
		:root {
			padding: 2em;
			background: #f8ede5;
			color: #242c43;
			font-family: "Eczar", serif;
			font-size: 16px;
			line-height: 1.5;
		}

		#app main {
			margin: auto;
			max-width: 40em;
		}

		#app h1 {
			margin-top: 0;
			font-family: "IM Fell English", serif;
		}

		#app h1 > div {
			font-family: "Eczar", serif;
			font-size: 1.5em;
		}

		#app h1 a {
			color: inherit;
			text-decoration: none;
		}

		#app h2 {
			break-before: page;
		}

		#app h2,
		#app h3 {
			margin-bottom: 0;
			break-after: avoid;
		}

		#app h2 + p,
		#app h3 + p,
		#app h3:first-child {
			margin-top: 0;
		}

		#app a {
			color: #405688;
		}

		#app ul {
			padding-left: 0;
			list-style: none;
		}

		#app ul li::before {
			content: "➶";
			margin-right: 0.5em;
		}

		#app li ul {
			margin-left: 1.3em;
		}

		#app li ul li::before {
			content: "➵";
		}

		@media print {
			:root {
				height: 210mm;
				width: 148mm;
				padding: 0;
				background: white;
				color: black;
				font-size: 24px;
			}

			#app main {
				max-width: 100%;
			}

			#app h1 {
				margin-top: 30vh;
				break-after: page;
			}

			#app a {
				color: inherit;
				text-decoration: none;
			}
		}
	</style>
</svelte:head>

<main>
	<slot />
</main>
