<script>
	import Social from '../components/Social.svelte';
	import LivePlayer from '../components/LivePlayer.svelte';
	import Presentation from '../components/Presentation.svelte';

	// export const prerender = true;
</script>

<h1>Piquet De Stream</h1>

<LivePlayer />
<Social />
<Presentation />

<style>
	h1 {
		text-shadow: 0px 0px 1.3px rgba(0, 0, 0, 0.162), 0px 0px 4.5px rgba(0, 0, 0, 0.238),
			0px 0px 20px rgba(0, 0, 0, 0.4);
	}
</style>
