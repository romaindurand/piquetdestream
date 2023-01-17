<script>
	import HelloAssoIcon from './HelloAssoIcon.svelte';
	import TwitchIcon from './TwitchIcon.svelte';
	import TwitterIcon from './TwitterIcon.svelte';
</script>

<ul>
	<li>
		<a href="https://twitter.com/PiquetDeStream" target="_blank" rel="noreferrer" title="Twitter">
			<TwitterIcon />
			Twitter
		</a>
	</li>
	<li>
		<a href="https://twitch.tv/piquetdestream" target="_blank" rel="noreferrer" title="Twitch">
			<TwitchIcon />
			Twitch
		</a>
	</li>
	<li>
		<a
			href="https://www.helloasso.com/associations/caisse-de-solidarite-2/formulaires/2"
			target="_blank"
			rel="noreferrer"
			title="Cagnotte"
		>
			<HelloAssoIcon />
			Cagnotte
		</a>
	</li>
</ul>

<style>
	ul {
		list-style: none;
		display: flex;
		justify-content: space-around;
		padding: 0;
	}

	li a {
		text-decoration: none;
		color: #fff;
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
		align-items: center;
		text-align: center;
		text-transform: uppercase;
	}

	li a:hover {
		font-weight: bold;
	}
</style>
