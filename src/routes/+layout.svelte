<script>
	import '$lib/base.css';
</script>

<svelte:head>
	<title>Piquet De Stream</title>
</svelte:head>

<div class="content">
	<slot />
</div>

<style>
	.content {
		max-width: 800px;
		margin: 0 auto;
	}
</style>
