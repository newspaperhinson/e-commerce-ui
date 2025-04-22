<script lang="ts">
	import { Lightbulb } from '@lucide/svelte';
	import type { IconProps } from '@lucide/svelte';

	interface Props extends IconProps {}

	let props: Props = $props();
</script>

<Lightbulb {...props} />
