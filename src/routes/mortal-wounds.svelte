<script lang="ts">
	import BasicMove from '$lib/components/BasicMove.svelte';
</script>

<svelte:head>
	<title>dungeonpunk: mortal wounds</title>
</svelte:head>

<main>
	<h1>
		dungeonpunk
		<div>mortal wounds</div>
	</h1>

	<section>
		<h2>the introduction</h2>

		<p>
			This is a hack for dungeonpunk by Ash McAllen, Sidney Icarus, and Melody Watson, a
			fiction-telling game about exploring a fantasy world and going on adventures.
		</p>

		<p>
			In dungeonpunk, damage is represented by Hit Points (HP). As you take damage, you lose HP, and
			when you have 0 HP or less remaining, you fall unconscious or die. This hack replaces that
			concept with Wounds and leans on the existing concept of Stress, an abstraction for physical
			and mental exhaustion.
		</p>

		<p>
			Instead of HP, a creature has a maximum number of Wounds. When you take damage from sources
			that can be dodged, deflected, or otherwise avoided, you gain Stress, but when you are
			encumbered, you are too tired and weighed down to protect yourself and start taking Wounds
			instead.
		</p>

		<p>
			In this way, Stress represents minor cuts and bruises as well as physical and mental
			exhaustion. They’re easy to heal, and after some rest, don’t interfere with your ability to
			fight, but if you’re too tired to protect yourself, you’re going to start taking real damage
			in the form of Wounds. Take too many of those and you’re likely to die.
		</p>
	</section>

	<section>
		<h2>the changes</h2>

		<h3>creating a character</h3>

		<p>
			When creating a character, instead of HP, you have 1+CON maximum Wounds. Whenever your CON
			changes, so does your maximum Wounds. Otherwise create your character as normal.
		</p>

		<BasicMove name="carry">
			<p>
				When you carry gear and Stress that exceeds 12+CON+WIS Weight, you become encumbered. While
				encumbered, you receive a -1 dice penalty to all rolls and cannot push yourself, assist
				others, or use any move that could make you gain Stress.
			</p>
		</BasicMove>

		<BasicMove name="rest">
			<p>
				When you take time to rest and recover, you lose 1d3 Stress for each hour you spend doing
				so.
			</p>
		</BasicMove>

		<BasicMove name="damage">
			<p>
				When you successfully hurt something or are hurt by something, gain the listed Wounds or
				give the listed Wounds to the target, as relevant:
			</p>
			<ul>
				<li>Minor damage: 0 (bumps, cuts, bruises)</li>
				<li>Standard damage: 1 (an attack with a weapon)</li>
				<li>Serious damage: 2 (incapacitation or maiming)</li>
				<li>Deadly damage: 3 (death)</li>
				<li>Catastrophic damage: 4 (capable of destroying a house)</li>
			</ul>
			<p>
				Worn armour reduces physical damage taken by Wounds equal to its weight. If armour absorbs
				any incoming damage it becomes dented, cracked, damaged, or destroyed, reducing its
				effectiveness by the number of Wounds it absorbed.
			</p>
		</BasicMove>

		<BasicMove name="collapse">
			<p>When you reach your maximum Wounds, you fall unconscious.</p>
		</BasicMove>

		<BasicMove name="die">
			<p>When you exceed your maximum Wounds, roll FATE.</p>
			<ul>
				<li>On a success: You fall unconscious.</li>
				<li>On a twist: The GM presents an opportunity to survive, but at a cost.</li>
				<li>On a failure: You die.</li>
			</ul>
		</BasicMove>
	</section>

	<section>
		<h2>the new</h2>

		<BasicMove name="avoid damage">
			<p>
				When you would be hurt by something and the source of that hurt can be dodged, deflected, or
				otherwise avoided, gain the listed Stress, as relevant, instead of taking any Wounds:
			</p>
			<ul>
				<li>Minor damage: 1 (bumps, cuts, bruises)</li>
				<li>Standard damage: 1d6 (an attack with a weapon)</li>
				<li>Serious damage: 2d6 (incapacitation or maiming)</li>
				<li>Deadly damage: 3d6 (death)</li>
				<li>Catastrophic damage: 4d6 (capable of destroying a house)</li>
			</ul>
			<p>
				Using a wielded weapon or shield to deflect physical damage reduces the Stress caused by an
				amount equal to its weight.
			</p>
		</BasicMove>

		<BasicMove name="let something go">
			<p>
				When you need to drop something in a hurry, such as if you are encumbered and under attack,
				roll FATE:
			</p>
			<ul>
				<li>
					On a success: Choose one:
					<ul>
						<li>It’s damaged in the process</li>
						<li>It rolls, slides, or is kicked away and becomes hard to find or reach later</li>
						<li>You let your guard down and take damage from a nearby threat</li>
					</ul>
				</li>
				<li>On a twist: Choose two.</li>
			</ul>
		</BasicMove>

		<BasicMove name="tend to wounds">
			<p>
				When you take time to patch yourself up or have someone patch you up and you rest, you lose
				1 Wound for each day you spend doing so.
			</p>
		</BasicMove>
	</section>

	<section>
		<h2>the conversion</h2>

		<p>For every 4 HP a creature had, give that creature 1 maximum Wound.</p>

		<p>
			For every 1d6 damage or healing something did, convert it to 1d6 Stress or 1 Wound depending
			on the context.
		</p>

		<p>For every 1 Stress something removed, make it 1d3 Stress.</p>
	</section>
</main>
