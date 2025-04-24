<script lang="ts">
	import { page } from '$app/state';
	import { ShoppingCart } from '@lucide/svelte';

	import Logo from '$lib/components/atoms/Logo.svelte';

	const navs = [{ href: '/shop', label: 'Shop' }];

	console.log(page.url.pathname);
</script>

<header
	class="bg-surface-50-950 text-surface-950-50 flex items-center justify-between px-8 py-4 shadow-md"
>
	<a href="/" class="flex items-center gap-2">
		<Logo class="h-8 w-8" fill="currentColor" />
		<p class="text-xl font-bold">LogicMart</p>
	</a>
	<div class="flex items-center gap-2">
		<nav class="mx-4 flex gap-6">
			{#each navs as nav}
				<a
					href={nav.href}
					class="
            font-medium
            hover:underline
            {page.url.pathname === nav.href ? 'text-primary-500' : ''}
					"
				>
					{nav.label}
				</a>
			{/each}
		</nav>
		<div class="relative cursor-pointer">
			<span class="badge-icon preset-filled-surface-500 absolute -top-4 -right-4 z-10 h-2 w-2"
				>3</span
			>
			<ShoppingCart />
		</div>
	</div>
</header>
