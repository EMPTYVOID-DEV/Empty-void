<script lang="ts">
	import Description from '$lib/components/core/description.svelte';
	import Units from '$lib/components/core/units.svelte';
	import { colorsMap, type units } from '$lib/utils/consts';
	import { onMount } from 'svelte';
	let description = `I'm Keskas Aymen, a 22-year-old independent web developer based in Algeria. My passion lies in crafting exceptional user interfaces, utilizing the latest and most advanced tools available, this year i am pursing a master's degree in cybersecurity.`;
	let awards: units = [
		{
			date: { day: 5, month: 'Jun', year: 2023 },
			title: "Bachelor's degree , Computer science",
			description:
				'I got Bachelors degreen in computer science at ferhat abbas university with score equal to 16.18.',
			href: 'https://fsciences.univ-setif.dz/',
			tags: ['Bachelors', 'computer science']
		}
	];
	onMount(() => {
		document.documentElement.style.setProperty('--primary', colorsMap.get('about'));
	});
</script>

<div class="about">
	<Description header="About" {description} />
	<div class="awards">
		<h3>Awards</h3>
		<Units units={awards} />
	</div>
</div>

<style>
	.about {
		width: 80%;
		display: flex;
		flex-direction: column;
		padding-left: 5%;
		gap: 40px;
	}
	.awards {
		width: 100%;
		display: flex;
		flex-direction: column;
		gap: 20px;
	}

	.awards h3 {
		color: var(--primary);
		align-self: center;
		padding-bottom: 5px;
		border-bottom: 3px solid var(--primary);
	}

	@media screen and (width < 768px) {
		.about {
			width: 95%;
		}
	}
</style>
