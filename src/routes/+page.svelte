<script>
	import Social from '../components/Social.svelte';
	import LivePlayer from '../components/LivePlayer.svelte';
	import Presentation from '../components/Presentation.svelte';

	// export const prerender = true;
</script>

<img src="./logo_black.png" alt="Piquet De Stream" />
<LivePlayer />
<Social />
<Presentation />

<style>
	img {
		position: relative;
		width: 50%;
		left: 50%;
		transform: translateX(-50%);
	}
</style>
