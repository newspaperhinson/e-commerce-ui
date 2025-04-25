<script lang="ts">
	import { ChevronLeft, ChevronRight } from '@lucide/svelte';
	import type { HTMLImgAttributes } from 'svelte/elements';

	const buttonClass = 'h-full cursor-pointer bg-secondary-50-950 p-4';

	const slides: HTMLImgAttributes[] = [
		{ src: 'img1.jpg', alt: 'img1' },
		{ src: 'img2.jpg', alt: 'img2' },
		{ src: 'img3.jpg', alt: 'img3' },
		{ src: 'img4.jpg', alt: 'img4' },
		{ src: 'img5.jpg', alt: 'img5' }
	];

	let currentSlideIndex = $state(0);

	const handleNextSlide = () => {
		currentSlideIndex = (currentSlideIndex + 1) % slides.length;
	};

	const handlePrevSlide = () => {
		currentSlideIndex = (currentSlideIndex - 1 + slides.length) % slides.length;
	};
</script>

<div class="bg-primary-50-950/50 flex h-64 items-center md:h-160">
	<button class={buttonClass} onclick={handlePrevSlide}>
		<ChevronLeft />
	</button>
	<div class="h-full w-full" id="carousel">
		{#if slides?.[currentSlideIndex]}
			<div class="flex h-full w-full flex-col items-center justify-center gap-4 text-2xl">
				<p>{slides[currentSlideIndex].src}</p>
			</div>
		{/if}
	</div>
	<button class={buttonClass} onclick={handleNextSlide}>
		<ChevronRight />
	</button>
</div>
