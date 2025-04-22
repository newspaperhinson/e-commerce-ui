<script lang="ts">
	import { ShoppingCart } from '@lucide/svelte';

	import Logo from '$lib/components/atoms/Logo.svelte';
</script>

<header
	class="bg-surface-50-950 text-surface-950-50 flex items-center justify-between px-8 py-4 shadow-md"
>
	<a href="/" class="flex items-center gap-2">
		<Logo class="h-8 w-8" fill="currentColor" />
		<p class="text-xl font-bold">LogicMart</p>
	</a>
	<div class="relative cursor-pointer">
		<span class="badge-icon preset-filled-surface-500 absolute -top-4 -right-4 z-10 h-2 w-2">3</span
		>
		<ShoppingCart />
	</div>
</header>
