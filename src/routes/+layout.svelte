<script lang="ts">
	import '../app.css';

	import { IconContext } from 'phosphor-svelte';

	let { children } = $props();
</script>

<IconContext values={{ size: 24 }}>
	{@render children()}
</IconContext>
