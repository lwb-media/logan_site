<script lang="ts">
	import { WavyBackground } from '$lib/components/ui/WavyBackground';
 import { CalendlyEmbed } from '$lib/components/CalendlyEmbed';
 import { StickyScrollReveal } from '$lib/components/ui/StickyScrollReveal';
 import { BentoGrid, BentoGridItem } from '$lib/components/ui/BentoGrid';

 //IMPORTANT VARIABLES
 const CALENDLY_LINK = "https://calendly.com/lwbgrowthagency/60min";

	const items = [
		{
			title: 'The Dawn of Innovation',
			description: 'Explore the birth of groundbreaking ideas and inventions.',
			className: 'md:col-span-2',
			icon: undefined
		},
		{
			title: 'The Digital Revolution',
			description: 'Dive into the transformative power of technology.',
			className: 'md:col-span-1',
			icon: undefined
		},
		{
			title: 'The Art of Design',
			description: 'Discover the beauty of thoughtful and functional design.',
			className: 'md:col-span-1',
			icon: undefined
		},
		{
			title: 'The Power of Communication',
			description: 'Understand the impact of effective communication in our lives.',
			className: 'md:col-span-2',
			icon: undefined
		}
	];

</script>
<div class="w-full p-5">
 <!-- Top Logo Section -->
 <div class="absolute z-10 w-full flex justify-center items-center left-0">
  <img src={"/logos/transparent-full-logo.png"} alt="LWB Media" class="w-48"/>
 </div>

 <!-- Introduction Header -->
 <WavyBackground className="flex flex-col items-center p-10 z-0" >
  <h2
   class="bg-opacity-50 bg-gradient-to-b from-neutral-50 to-neutral-400 bg-clip-text text-center text-4xl font-bold text-transparent md:text-7xl"
  >
  We Help Influencers Boost <br /> Their Revenue Via Paid Communities
  </h2>
  <p class="mx-auto mt-4 max-w-lg text-center text-base font-normal text-neutral-300">
   Stop letting companies rent out your audience. It's time to directly monetize your audience, build a paid community and scale your revenue.
  </p>
 </WavyBackground>

 <!-- Calendly Embed -->
 <CalendlyEmbed url={CALENDLY_LINK} />



 <!-- Philosophy -->
 <StickyScrollReveal content={[
		{
			title: 'Collaborative Editing',
			description:
				'Work together in real time with your team, clients, and stakeholders. Collaborate on documents, share ideas, and make decisions quickly. With our platform, you can streamline your workflow and increase productivity.'
		},
		{
			title: 'Real time changes',
			description:
				'See changes as they happen. With our platform, you can track every modification in real time. No more confusion about the latest version of your project. Say goodbye to the chaos of version control and embrace the simplicity of real-time updates.'
		},
		{
			title: 'Version control',
			description:
				"Experience real-time updates and never stress about version control again. Our platform ensures that you're always working on the most recent version of your project, eliminating the need for constant manual updates. Stay in the loop, keep your team aligned, and maintain the flow of your work without any interruptions."
		},
		{
			title: 'Running out of content',
			description:
				"Experience real-time updates and never stress about version control again. Our platform ensures that you're always working on the most recent version of your project, eliminating the need for constant manual updates. Stay in the loop, keep your team aligned, and maintain the flow of your work without any interruptions."
		}
	]} />

<div class='w-full my-44'></div>

  <!-- Stats -->
  <BentoGrid className="max-w-4xl mx-auto md:auto-rows-[20rem]">
   {#each items as item, i (i)}
    <BentoGridItem title={item.title} description={item.description} className={item.className}>
     <div
      slot="header"
      class="flex h-full min-h-[6rem] w-full flex-1 rounded-xl border border-transparent bg-neutral-100 bg-dot-black/[0.2] [mask-image:radial-gradient(ellipse_at_center,white,transparent)] dark:border-white/[0.2] dark:bg-black dark:bg-dot-white/[0.2]"
     ></div>
     <svelte:component this={item.icon} slot="icon" class="h-4 w-4 text-neutral-500" />
    </BentoGridItem>
   {/each}
  </BentoGrid>
</div>
