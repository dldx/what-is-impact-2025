<script lang="ts">
	import '../styles/app.css'

	let { children } = $props()
</script>

<svelte:head>
	<title>What is Impact? - Tracker Group</title>
</svelte:head>

{@render children()}