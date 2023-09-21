<script lang="ts">
	import BasicMove from "$lib/components/BasicMove.svelte";
	import MoveResults from "$lib/components/MoveResults.svelte";
	import cover from "$lib/images/mortal-wounds-cover.png";
</script>

<svelte:head>
	<title>dungeonpunk: mortal wounds</title>
</svelte:head>

<main>
	<h1>
		<a href="..">dungeonpunk</a>
		<div>mortal wounds</div>
	</h1>

	<aside class="print-hint">
		Print this page or <a
			href="https://erbridge.itch.io/dungeonpunk-mortal-wounds"
			>download a copy from itch.io</a
		>!
	</aside>

	<section>
		<figure>
			<img
				src={cover}
				style="shape-outside: url({cover})"
				alt="A black woman in armour, fixing the bandage on her wounded leg. Her helmet, gauntlets, and sword lie on the ground beside her."
			/>
			<caption
				>Art by <a
					href="https://twitter.com/DemortaFantasy"
					target="_blank"
					rel="noopener noreferrer">Demorta</a
				></caption
			>
		</figure>

		<h2>what’s this?</h2>

		<p>
			This is a hack for <a
				href="https://acegiak.itch.io/dungeonpunk"
				target="_blank"
				rel="noopener noreferrer">dungeonpunk</a
			> by Ash McAllan, Sidney Icarus, and Melody Watson, a fiction-telling game
			about exploring a fantasy world and going on adventures.
		</p>

		<p>
			Normally in dungeonpunk, damage is represented by <strong
				>Hit Points (HP)</strong
			>. As you take damage, you lose HP, and when you have 0 HP or less
			remaining, you fall unconscious or die. This hack replaces that concept
			with <strong>Wounds</strong> and leans on the existing concept of
			<strong>Stress</strong>, an abstraction for physical and mental
			exhaustion.
		</p>

		<p>
			Instead of HP, a creature has a maximum number of Wounds. When you take
			damage from sources that can be dodged, deflected, or otherwise avoided,
			you gain Stress, but when you are encumbered, you are too tired and
			weighed down to protect yourself and start taking Wounds instead.
		</p>

		<p>
			In this way, Stress represents minor cuts and bruises as well as physical
			and mental exhaustion. They’re easy to heal, and after some rest, don’t
			interfere with your ability to fight, but if you’re too tired to protect
			yourself, you’re going to start taking real damage in the form of Wounds.
			Take too many of those and you’re likely to die.
		</p>
	</section>

	<section>
		<h2>creating a character</h2>

		<p>
			When creating a character, instead of HP, you have <strong
				>1+CON maximum Wounds</strong
			>. Whenever your CON changes, so does your maximum Wounds. Otherwise
			create your character as normal.
		</p>
	</section>

	<section>
		<h2>basic moves</h2>

		<BasicMove name="carry" replace>
			<p>
				When you <strong
					>carry gear and Stress that exceeds 12+CON+WIS Weight</strong
				>, you become encumbered. While encumbered, you receive a -1 dice
				penalty to all rolls and cannot push yourself, assist others, or use any
				move that could make you gain Stress.
			</p>
		</BasicMove>

		<BasicMove name="let something go">
			<p>
				When you need to <strong>drop something in a hurry</strong>, such as if
				you are encumbered and under attack, roll FATE.
			</p>
			<MoveResults>
				<span slot="success"
					>Choose one:
					<ul>
						<li>It’s damaged or destroyed in the process</li>
						<li>
							It rolls, slides, or is kicked away and becomes hard to find or
							reach later
						</li>
						<li>
							You let your guard down and take damage from a nearby threat
						</li>
					</ul></span
				>
				<span slot="twist">Choose two.</span>
			</MoveResults>
		</BasicMove>

		<BasicMove name="rest" replace>
			<p>
				When you take time to <strong>rest and recover</strong>, you lose 1d3
				Stress for each hour you spend doing so.
			</p>
		</BasicMove>

		<BasicMove name="tend to wounds">
			<p>
				When you take time to <strong>patch yourself up</strong> or
				<strong>have someone patch you up</strong>
				and you <strong>rest</strong>, you lose 1 Wound for each day you spend
				doing so.
			</p>
		</BasicMove>

		<BasicMove name="damage" replace>
			<p>
				When you <em>successfully</em> <strong>hurt something</strong> or
				<strong>are hurt by something</strong>, gain the listed Wounds or give
				the listed Wounds to the target, as relevant:
			</p>
			<ul>
				<li>Minor damage: 0 (bumps, cuts, bruises)</li>
				<li>Standard damage: 1 (an attack with a weapon)</li>
				<li>Serious damage: 2 (incapacitation or maiming)</li>
				<li>Deadly damage: 3 (death)</li>
				<li>Catastrophic damage: 4 (capable of destroying a house)</li>
			</ul>
			<p>
				Worn <strong>armour</strong> reduces physical damage taken by Wounds
				equal to its weight. If armour absorbs <strong>any</strong> incoming damage
				it becomes dented, cracked, damaged, or destroyed, reducing its effectiveness
				by the number of Wounds it absorbed.
			</p>
		</BasicMove>

		<BasicMove name="avoid damage">
			<p>
				When you <strong
					>would be hurt by something and the source of that hurt can be dodged,
					deflected, or otherwise avoided</strong
				>, gain the listed Stress, as relevant, instead of taking any Wounds:
			</p>
			<ul>
				<li>Minor damage: 1 (bumps, cuts, bruises)</li>
				<li>Standard damage: 1d6 (an attack with a weapon)</li>
				<li>Serious damage: 2d6 (incapacitation or maiming)</li>
				<li>Deadly damage: 3d6 (death)</li>
				<li>Catastrophic damage: 4d6 (capable of destroying a house)</li>
			</ul>
			<p>
				Using a <strong>wielded weapon</strong> or <strong>shield</strong> to deflect
				physical damage reduces the Stress caused by an amount equal to its weight.
			</p>
		</BasicMove>

		<BasicMove name="collapse" replace>
			<p>
				When you <strong>reach your maximum Wounds</strong>, you fall
				unconscious.
			</p>
		</BasicMove>

		<BasicMove name="die" replace>
			<p>When you <strong>exceed your maximum Wounds</strong>, roll FATE.</p>
			<MoveResults>
				<span slot="success">You fall unconscious.</span>
				<span slot="twist"
					>The GM presents an opportunity to survive, but at a cost.</span
				>
				<span slot="failure">You die.</span>
			</MoveResults>
		</BasicMove>
	</section>

	<section>
		<h2>converting other rules</h2>

		<p>For every 4 HP a creature had, give that creature 1 maximum Wound.</p>

		<p>
			For every 1d6 damage or healing something did, convert it to 1d6 Stress or
			1 Wound depending on the context.
		</p>

		<p>For every 1 Stress something removed, make it 1d3 Stress.</p>
	</section>
</main>

<style>
	.print-hint {
		font-style: italic;
	}

	figure {
		margin: 0;
	}

	figure > img,
	figure > caption {
		width: 100%;
	}

	figure > caption {
		margin-bottom: -2em;
		float: right;
		position: relative;
		top: -2em;
		text-align: right;
	}

	@media only screen and (min-width: 30rem) {
		figure > img,
		figure > caption {
			width: 80%;
		}

		figure > img {
			shape-margin: 2em;
			float: right;
		}
	}

	@media print {
		.print-hint {
			display: none;
		}

		figure > img {
			margin-top: 7em;
		}

		figure > caption {
			margin-bottom: 0;
			float: none;
			position: none;
			top: none;
		}
	}
</style>
