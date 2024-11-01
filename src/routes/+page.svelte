<script lang="ts">
	import { WavyBackground } from '$lib/components/ui/WavyBackground';
	import { CalendlyEmbed } from '$lib/components/CalendlyEmbed';
	import { StickyScrollReveal } from '$lib/components/ui/StickyScrollReveal';
	import { BentoGrid, BentoGridItem } from '$lib/components/ui/BentoGrid';
	

	//IMPORTANT VARIABLES
	const CALENDLY_LINK = 'https://calendly.com/lwbgrowthagency/60min';

	const items = [
		{
			title: 'Total Revenue Generated',
			stat: '$432 Thousand',
			className: 'md:col-span-2',
		},
		{
			title: 'Clients Helped',
			className: 'md:col-span-1',
		},
		{
			title: 'Offices',
			className: 'md:col-span-1',
		},
		{
			title: 'Services Offered',
			className: 'md:col-span-1',
		},
		{
			title: 'Total Ad Spend',
			className: 'md:col-span-1',
		}
	];
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
	</WavyBackground>

		<!-- Philosophy -->
		<StickyScrollReveal
		content={[
			{
				title: 'Philosophy',
				description: `At LWB Media, we believe influencers should own and maximize the full potential of their brand
and audience. For too long, influencers have allowed external companies to take avangage and
profit from their audience.`
			},
			{
				title: 'Mission',
				description: `Our mission is to empower influencers by helping them take control of
their revenue through building authentic, paid communities that foster deeper connections with
their audience and have lasting value.`
			},
			{
				title: 'Commitment',
				description: `We are committed to bridging the gap between
influencers and their audience, creating a future where creators are fully in control of their
community, impact, and financial success.`
			},
			{
				title: 'Success',
				description: `Our client success stories are legendary, and you could be next. We’d be honored to help you
achieve the same. Schedule your free call below. Add meet link`
			}
		]}
	/>
	
	<div class="w-full my-44"></div>

	<!-- Stats -->
	<div>
		<BentoGrid className="max-w-4xl mx-auto md:auto-rows-[20rem]">
			{#each items as item, i (i)}
				<BentoGridItem title={item.title} className={item.className}>
					<div
						slot="header"
						class="text-center align-middle w-full h-full"
					>
						<h1 class="text-pink-500">{item.stat}</h1>
					</div>
				</BentoGridItem>
			{/each}
		</BentoGrid>
	</div>

	<!-- Calendly Embed -->
	<CalendlyEmbed url={CALENDLY_LINK} />

	<div class="w-full my-44"></div>

	
</div>

<style lang="css">
	@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@1000&display=swap');

</style>