<script lang="ts">
	import { goto } from '$app/navigation';
	import { onMount } from 'svelte';

	let activeCard = 0;
	let backgroundColors = [
		'linear-gradient(to right, black, var(--gray-950))',
	 'linear-gradient(to right, black, var(--cyan-950))',
		'linear-gradient(to right, black, var(--indigo-950))',
		'linear-gradient(to right, black, var(--blue-950))'
	];
	let linearGradients = [
		'linear-gradient(to bottom right, var(--cyan-500), var(--emerald-500))',
		'linear-gradient(to bottom right, var(--pink-500), var(--indigo-500))',
		'linear-gradient(to bottom right, var(--orange-500), var(--yellow-500))'
	];
	let scrollYProgress = 0;

	export let content: { title: string; description: string; btn?: { link: string; text: string; }; }[] = [];

	let ref: HTMLDivElement;

	onMount(() => {
		const handleScroll = (event: Event) => {
			const target = event.target as HTMLElement;
			scrollYProgress = target.scrollTop / target.scrollHeight;
			const cardsBreakpoints = content.map((_, index) => index / content.length);

			cardsBreakpoints.forEach((breakpoint, index) => {
				if (scrollYProgress > breakpoint - 0.2 && scrollYProgress <= breakpoint) {
					activeCard = index;
				}
			});
		};

		ref.addEventListener('scroll', handleScroll);

		return () => {
			ref.removeEventListener('scroll', handleScroll);
		};
	});
</script>

<div
	bind:this={ref}
	style="background: {backgroundColors[activeCard % backgroundColors.length]}"
	class="relative flex h-[30rem] justify-center space-x-10 overflow-y-auto rounded-md p-10 transition ease-in-out no-scrollbar"
>
	<div class="div relative flex items-start px-4">
		<div class="max-w-2xl">
			{#each content as item, index (item.title + index)}
				<div class="my-20">
					<h2
						style="opacity: {activeCard === index ? 1 : 0.3}"
						class="text-2xl font-bold text-slate-100"
					>
						{item.title}
					</h2>
					<p
						style="opacity: {activeCard === index ? 1 : 0.3}"
						class="text-kg mt-10 max-w-sm text-slate-300"
					>
						{item.description}
						
					</p>
					{#if item?.btn?.link}
					<span class=" w-fit h-fit my-[36px]">
					<a 
					class="block my-4 px-8 py-2 w-fit bg-black text-white text-sm rounded-md font-semibold hover:bg-black/[0.8] hover:shadow-lg"
					href="{item?.btn.link}"
					>
					{item?.btn?.text}
				</a>
			</span>
					{/if}
		
		
				</div>
			{/each}
			<div class="h-40"></div>
		</div>
	</div>
	<div
		style="background: {linearGradients[activeCard % linearGradients.length]}"
		class="sticky top-10 h-60 w-80 overflow-hidden rounded-md bg-white lg:block flex flex-col content-center">
	<img src={"/logos/transparent-full-logo.png"}/>
</div>
</div>