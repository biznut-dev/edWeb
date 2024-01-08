<script lang="ts">
	import { onMount } from 'svelte';

	// export class Thingy {
	// 	title: string;
	// 	author: string;

	// 	constructor(title: string, author: string) {
	// 		this.title = title;
	// 		this.author = author;
	// 	}
	// }

	// main page content
	export let img: string;
	export let title: string;
	export let tools: string;
	export let accomplishments: Array<string>;
	export let time: string;

	// modal content
	export let video: string;
	export let game_link: string;
	export let description: string;
	export let showcase: Array<ShowcaseItem>;

	// TODO
	// export a list variable
	// create a function that adds elements from the list to the html and have it update automatically using $:s
	// maybe have two lists? (one called 'tools' another called 'accomplishments')

	let description_list: HTMLElement;
	let modal_button: HTMLElement;
	let modal_card: HTMLElement;
	let modal_list: HTMLElement;

	// Functions to open and close a modal
	function openModal() {
		modal_card.classList.add('is-active');
	}

	function closeModal() {
		modal_card.classList.remove('is-active');
	}

	onMount(() => {
		//jq("#add").append(additional);

		// add accomplishments to description list
		accomplishments.forEach(function (item: string, index: number) {
			let listItem: HTMLElement = document.createElement('li');
			listItem.innerText = item;
			description_list.append(listItem);
		});

		// Add a click event on various child elements to close the parent modal
		(
			document.querySelectorAll(
				'.modal-background, .modal-close, .modal-card-head .delete, .modal-card-foot .button'
			) || []
		).forEach(($close: Element) => {
			const $target: Element | null = $close.closest('.modal');

			$close.addEventListener('click', () => {
				closeModal();
			});
		});

		// add showcase items to modal
		if (showcase) {
			showcase.forEach(function (item: ShowcaseItem, index: number) {
				// create the title for the showcase and italicize and append it
				let title: HTMLElement = document.createElement('p');
				let italics: HTMLElement = document.createElement('i');
				italics.innerText = item.title;
				modal_list.after(title);
				title.append(italics);

				// create the gif for the showcase and append it
				let gif: HTMLElement = document.createElement('img');
				gif.setAttribute('alt', '');
				gif.setAttribute('width', '100%');
				gif.setAttribute('src', item.gif);

				modal_list.after(gif);
			});
		}
	});
</script>

<div class="column is-4-fullhd is-6-tablet">
	<div class="card">
		<div class="card-image">
			<figure class="image is-4by3 button">
				<img class="pixelated" src={img} alt="Placeholder image" on:click={openModal} />
			</figure>
		</div>
		<div class="card-content">
			<div class="media-content">
				<p class="title is-4" style="margin-bottom: 10px;">{title}</p>
				<p class="title is-6" style="margin-bottom: 5px;">{tools}</p>
			</div>
			<div class="content" style="margin-bottom: 5px;">
				<!-- {description} -->
				<ul bind:this={description_list} style="margin-top: 0px;" />
			</div>
			<div class="content">
				<time>{time}</time>
			</div>
		</div>
	</div>
</div>

<div id="modal-ter" class="modal" bind:this={modal_card}>
	<div class="modal-background" />
	<div class="modal-card">
		<header class="modal-card-head">
			<p class="modal-card-title">{title} <a href={game_link}>(Play Game)</a></p>
			<button class="delete" aria-label="close" />
		</header>
		<section class="modal-card-body">
			<div class="content">
				<div class="container">
					<iframe class="responsive-iframe" title="" width="100%" src={video} />
				</div>
				<h3 class="title">Description</h3>
				<p>{description}</p>
				<h3 class="title" bind:this={modal_list}>What I Made</h3>
				<!-- <p><i>Thing #1</i></p> -->
				<!-- <img width="100%" src="/src/media/big-mow1.gif" alt="" /> -->
			</div>
		</section>
		<footer class="modal-card-foot">
			<button class="button is-success">Close</button>
		</footer>
	</div>
</div>
