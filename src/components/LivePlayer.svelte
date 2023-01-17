<div class="player-wrapper">
	<iframe
		src="https://player.twitch.tv/piquetdestream"
		width="100%"
		height="100%"
		allowfullscreen
		title="player twitch live"
		class="live-player"
	/>
</div>

<style>
	.player-wrapper {
		position: relative;
		padding-bottom: 56.25%;
		border-radius: 3px;
		box-shadow: 0px 0px 1.3px rgba(0, 0, 0, 0.162), 0px 0px 4.5px rgba(0, 0, 0, 0.238),
			0px 0px 20px rgba(0, 0, 0, 0.4);
	}

	.live-player {
		border-radius: 3px;
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		border: 0;
	}

	@media (max-width: 800px) {
		.live-player {
			width: 100%;
		}
	}
</style>
