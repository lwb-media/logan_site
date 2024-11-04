<script lang="ts">
	import { WavyBackground } from '$lib/components/ui/WavyBackground';
	import { CalendlyEmbed } from '$lib/components/CalendlyEmbed';
	import { StickyScrollReveal } from '$lib/components/ui/StickyScrollReveal';
	import { BentoGrid, BentoGridItem } from '$lib/components/ui/BentoGrid';
	import { bentoItems, CALENDLY_LINK, philosophy, INSTAGRAM_LINK, MAIL_LINK, ACCENT_COLOR } from '$lib/content';
	import { Instagram, Mail } from 'lucide-svelte';
	import '../app.css';

	const words = [{ text: 'Test' }, { text: 'So' }, { text: 'Sigma0' }, { text: 'Rizz' }];
</script>

<div class="w-full p-5">
	<!-- Top Logo Section -->
	<div class="absolute z-10 w-full flex justify-center items-center left-0">
		<img src={'/logos/transparent-full-logo.png'} alt="LWB Media" class="w-48" />
	</div>

	<!-- Introduction Header -->
	<WavyBackground className="flex flex-col items-center p-10 z-0">
		<h2
			class="bg-opacity-50 bg-gradient-to-b from-neutral-50 to-neutral-400 bg-clip-text text-center text-4xl font-bold text-transparent md:text-7xl"
		>
			We Help Influencers Boost <br /> Their Revenue Via Paid Communities
		</h2>

		<p class="mx-auto mt-4 max-w-lg text-center text-base font-normal text-neutral-300">
			Stop letting companies rent out your audience. It's time to directly monetize your audience,
			build a paid community and scale your revenue.
		</p>
		<a 
		class={"block my-4 px-8 py-2 w-fit text-white text-sm rounded-md font-semibold hover:bg-black/[0.8] hover:shadow-lg bg-sky-500"}
		href="#calendly"
		> 
		Speak to our Team Today
	</a>
	</WavyBackground>

	<!-- Philosophy -->


	<div class="w-full my-[30vh]"></div>

	<!-- Stats -->
	<div>
		<BentoGrid className="max-w-4xl md:auto-rows-[20rem]">
			{#each bentoItems as item, i (i)}
				<BentoGridItem title={item.title} className={item.className}>
					<div slot="header" class="w-full h-full flex justify-center items-center">
						<span class={" font-nunito text-[5vh] text-sky-500"}>{item.stat}</span>
					</div>
				</BentoGridItem>
			{/each}
		</BentoGrid>
	</div>

	<div class="w-full my-[30vh]"></div>

	<!-- Calendly Embed -->
	<CalendlyEmbed url={CALENDLY_LINK} />

	<div class="w-full my-[5vh]"></div>

	<!-- Footer -->
	<div class="w-full flex flex-row justify-center">
		<div class="block">
			<span class="text-white">Contact Us</span>
			<br />
			<span class="flex flex-row">
				<a href={INSTAGRAM_LINK} target="_blank">
					<Instagram class="m-2" color="white" />
				</a>
				<a href={MAIL_LINK} target="_blank">
					<Mail class="m-2" color="white" />
				</a>
			</span>
		</div>
	</div>
</div>
