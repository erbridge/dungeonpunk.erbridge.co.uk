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
			background: white;
			color: black;
		}

		a {
			color: inherit;
			text-decoration: none;
		}
	}
</style>
