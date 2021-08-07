<slot />

<style global>
	@import 'normalize.css';

	:root {
		padding: 2em;
		background: #f8ede5;
		color: #242c43;
		font-family: 'Eczar', serif;
		font-size: 16px;
		line-height: 1.5;
	}

	body {
		margin: auto;
		max-width: 40em;
	}

	h1 {
		margin-top: 0;
		font-family: 'IM Fell English', serif;
	}

	h1 > div {
		font-family: 'Eczar', serif;
		font-size: 1.5em;
	}

	h1 a {
		color: inherit;
		text-decoration: none;
	}

	h2 {
		break-before: page;
	}

	h2,
	h3 {
		margin-bottom: 0;
		break-after: avoid;
	}

	h2 + p,
	h3 + p,
	h3:first-child {
		margin-top: 0;
	}

	a {
		color: #405688;
	}

	ul {
		padding-left: 0;
		list-style: none;
	}

	ul li::before {
		content: '➶';
		margin-right: 0.5em;
	}

	li ul {
		margin-left: 1.3em;
	}

	li ul li::before {
		content: '➵';
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

		body {
			max-width: 100%;
		}

		h1 {
			margin-top: 30vh;
			break-after: page;
		}

		a {
			color: inherit;
			text-decoration: none;
		}
	}
</style>
