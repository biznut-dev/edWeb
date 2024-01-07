<script lang="ts">
	import Project from './Project.svelte';
	import type { ShowcaseItem } from './Project.svelte';
	import { onMount } from 'svelte';

	// big mow stuff
	let bigMowList: Array<string> = [];
	bigMowList.push('Submitted for BigMode Game Jam 2023');
	bigMowList.push('Implemented custom movement using the physics engine and Enhanced Input system');
	bigMowList.push(
		'Practiced collaborative coding/version control to implement various gameplay mechanics'
	);

	let bigMowShowcase: ShowcaseItem[] = [
		{
			title: 'Flower, grass, and grass enemy models',
			gif: '/src/media/big-mow3.gif'
		},
		{
			title: 'Flower collection, big mode transformation, and mini-mower projectile shooting',
			gif: '/src/media/big-mow2.gif'
		},
		{
			title: 'Camera, controls, movement, collision, and rage level (speed level) UI',
			gif: '/src/media/big-mow1.gif'
		}
	];

	// lorelei stuff
	let loreleiList: Array<string> = [];
	loreleiList.push('Making in team of 8 for my Senior Capstone');
	loreleiList.push('Implementing/designing dynamic hybrid turn-based/real-time RPG combat system');
	loreleiList.push('Practicing software engineering principles and programming patterns');

	// simulacra stuff
	let simulacraList: Array<string> = [];
	simulacraList.push('Made for my Rhetoric of Games class');
	simulacraList.push('Implemented a flamethrower and fireball mechanic');
	simulacraList.push('Experimented with the Niagara and Cascade Particle Systems');

	// machina stuff
	let machinaList: Array<string> = [];
	machinaList.push('Made for my Advanced Level Design class');
	machinaList.push(
		'Learned basics of Unreal Engine programming (input, collision, movement, animations, materials, instancing, level sequences)'
	);
	machinaList.push('Learned basics of the Unreal Level Editor and lighting/rendering engine');

	// valley stuff
	let valleyList: Array<string> = [];
	valleyList.push('Made in a team of 5 for my Indie Game Development class');
	valleyList.push('Implemented an inventory/item system');
	valleyList.push('Implemented a puzzle piece mini-game');

	onMount(() => {
		//jq("#add").append(additional);
		//document.getElementById("add")?.insertAdjacentElement('afterend', document.createElement("br"));
	});
</script>

<div class="columns">
	<div class="column is-10 is-offset-1">
		<section class="section">
			<h1 class="title">Projects</h1>

			<div class="columns is-multiline">
				<Project
					img="/src/media/big-mow.png"
					title="Big Mow"
					tools="Unreal Engine 5, Blueprints, C++, Blender"
					accomplishments={bigMowList}
					time="Released on itch.io on Dec 16, 2023"
					video="https://drive.google.com/file/d/1mvt6HvhUnsBe-eU7S4jKFXiG4lNoKuXr/preview"
					game_link="https://biznut.itch.io/big-mow"
					description="My friend and I made this project for the BigMode 2023 game jam. The theme of the jam was 'mode.' 
					We interpreted this in two ways: as a pun ('mowed') and as a gameplay mechanic in which the player can go into a 
					powered up mode. The gameplay consists of mowing over continuously growing grass as the speed of the mower increases. 
					When a patch of grass reaches its max height it transforms into a permanent obstacle. After collecting 3 gear flowers 
					the mower goes into 'big mode' where the player can run over the grass obstacles and shoot mini mower projectiles."
					showcase={bigMowShowcase}
				/>
				<Project
					img="/src/media/lorelei-export.png"
					title="Goodbye Lorelei (WIP)"
					tools="Unity, C#"
					accomplishments={loreleiList}
					time="ETA 2024"
					video=""
					game_link=""
					description=""
				/>
				<Project
					img="/src/media/simulacra-thumb.png"
					title="Layers of Simulacra"
					tools="Unreal Engine 5, Blueprints, C++"
					accomplishments={simulacraList}
					time="Made during fall semester 2023"
					video="https://drive.google.com/file/d/14NuUDW0RPJjO3voKuYRM8GXmvkidgrsR/preview"
					game_link=""
					description=""
				/>
				<Project
					img="/src/media/death-machina.png"
					title="Death Machina"
					tools="Unreal Engine 5, Blueprints"
					accomplishments={machinaList}
					time="Made during fall semester 2023"
					video="https://drive.google.com/file/d/1rTP6KkNsBcm1U5FdNRpAoxSWp-ri9Wxd/preview"
					game_link=""
					description=""
				/>
				<Project
					img="/src/media/"
					title="Uncanny Valley"
					tools="Unity, C#"
					accomplishments={valleyList}
					time="Released on itch.io on Dec 07, 2022"
					video="https://drive.google.com/file/d/1Vx4MNRcPaZMY2J5Pbnw78kX2S5Km8IAA/preview"
					game_link="https://biznut.itch.io/uncanny-valley"
					description=""
				/>
			</div>
		</section>

		<section class="section">
			<h1 class="title">About Me</h1>

			<div class="columns is-mobile is-multiline is-centered">
				<div class="column is-three-fifths">
					<p class="subtitle pl-3 pr-3 pt-3" style="font-size: 28px;">
						Hi, I'm Ethan. I'm a gameplay programmer with various projects in Unity and Unreal
						Engine seeking opportunities in the gaming industry. I am very passionate about game
						development and programming, and I constantly seek to improve at my craft. My main area
						of expertise is mechanics and systems programming; though, I also have some knowledge of
						shaders and the render pipelines as well. During my free-time, I enjoy producing music,
						rock climbing, and competing in Super Smash Bros. tournaments.
					</p>
				</div>
				<div class="column is-narrow">
					<figure class="image is-256x256">
						<img class="is-rounded" src="/src/media/headshot1-modified.png" />
					</figure>
				</div>
			</div>
		</section>

		<!-- <section class="section">
			<h1 class="title">Skills</h1>
		</section> -->
	</div>
</div>
