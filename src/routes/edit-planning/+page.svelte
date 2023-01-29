<script>
	import { onMount } from 'svelte';

	/** @type HTMLDialogElement */
	let editor;
	let date = 'Dimanche 13.12';
	let editorOpen = false;
	/**
	 * @typedef {Object} Event
	 * @property {string} time
	 * @property {string} title
	 * @property {string} author
	 *
	 * @type {Event[]}
	 */
	let events = [
		{
			time: '9h-10h',
			title: 'Grève workshop',
			author: '@toto'
		}
	];

	onMount(() => {
		window.addEventListener('keyup', (e) => {
			if (e.key === 'Escape') {
				toggleEditor();
			}
		});
	});

	function toggleEditor() {
		if (editorOpen) {
			editor.close();
			editorOpen = false;
		} else {
			editor.showModal();
			editorOpen = true;
		}
	}

	/** @param {number} i */
	function deleteEvent(i) {
		events = events.filter((_, index) => index !== i);
	}

	/**
	 * @param {number} i
	 */
	function moveUp(i) {
		if (i === 0) return;
		const event = events[i];
		events = events.filter((_, index) => index !== i);
		events = [...events.slice(0, i - 1), event, ...events.slice(i - 1)];
	}

	function createEvent() {
		events = [...events, { time: '9h-10h', title: 'vide', author: '@toto' }];
	}
</script>

<div class="background">
	<div class="colonne" />
	<button class="logo" on:click={toggleEditor} />
	<div class="flamme" />
	<div class="date">{date}</div>
	<div class="events">
		{#each events as event}
			<div class="event">
				<div class="time">{event.time}</div>
				<div class="event-right">
					<div class="full-title">
						<span>•</span>
						<span class="title">{event.title}</span>
					</div>
					<div class="full-author">
						<span>avec</span>
						<span class="author">{event.author}</span>
					</div>
				</div>
			</div>
		{/each}
	</div>
</div>

<dialog bind:this={editor}>
	<div>
		<h1>Date</h1>
		<input type="text" bind:value={date} />
	</div>
	<div>
		<h1>Events</h1>
		<button on:click={createEvent}> créer </button>
		{#each events as event, i}
			<div>
				<input type="text" bind:value={event.time} />
				<input type="text" bind:value={event.title} />
				<input type="text" bind:value={event.author} />
				<button on:click={() => deleteEvent(i)}>X</button>
				<button on:click={() => moveUp(i)}>↑</button>
				<button on:click={() => moveUp(i + 1)}>↓</button>
			</div>
		{/each}
	</div>
</dialog>

<style>
	dialog {
		background-color: rgba(0, 0, 0, 0.2);
		border: 1px solid black;
		border-radius: 3px;
	}

	dialog h1 {
		text-shadow: 0 0 2px white;
	}

	.flamme {
		position: absolute;
		bottom: 0;
		left: 20px;
		width: 271px;
		height: 310px;
		background: url('$lib/images/flamme.png') no-repeat center;
		background-size: cover;
	}

	.logo {
		position: absolute;
		top: 20px;
		left: 20px;
		width: 120px;
		height: 121px;
		background: url('$lib/images/logo.png') no-repeat center;
		background-size: cover;
		border: none;
		cursor: pointer;
	}

	.logo:focus {
		outline: none;
	}

	.background {
		position: absolute;
		top: 0;
		left: 0;
		width: 1200px;
		height: 100%;
		background: url('$lib/images/fond.jpg') no-repeat center center fixed;
		background-size: cover;
	}

	.colonne {
		position: absolute;
		top: 0;
		left: 0;
		width: 327px;
		height: 100%;
		background-color: #ba2c2b;
	}

	.date {
		margin-left: 425px;
		color: #b12b2e;
		text-shadow: 4px 0 0 #c99591;
		position: relative;
		font-size: 83px;
		font-family: 'PermanentMarker';
	}

	.events {
		color: black;
		position: relative;
	}

	.event {
		display: flex;
	}

	.event-right {
		margin-left: 33px;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}

	.full-author {
		margin-top: -10px;
		font-family: 'duepuntozero';
		font-size: 46px;
		display: inline-block;
		margin-left: 25px;
	}

	.author {
		color: #b12b2e;
	}

	.full-title {
		display: inline-block;
		text-transform: uppercase;
		font-family: 'miso';
		font-size: 46px;
	}
	.title {
		border-bottom: 3px solid black;
	}

	.time {
		font-family: 'Pelita';
		font-size: 58px;
		width: 327px;
		text-align: center;
		margin-top: 25px;
	}
</style>
