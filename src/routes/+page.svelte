<script lang="ts">
	import { WavyBackground } from '$lib/components/ui/WavyBackground';
	import { CalendlyEmbed } from '$lib/components/CalendlyEmbed';
	import { SpeakToTeamButton } from '$lib/components/SpeakToTeamButton';
	import { CircleX } from 'lucide-svelte';
	import '../app.css';
	const CALENDLY_LINK = 'https://calendly.com/lwbgrowthagency/60min';
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

		<span class="flex flex-row justify-center">
			<SpeakToTeamButton />
		</span>
	</WavyBackground>

	
	<div class="w-full my-[10vh]"></div>

	<!-- Stats and Philosophy -->
	<div class="w-full flex flex-wrap flex-row justify-evenly">
			<!-- Stats -->
		<div class="w-full sm:w-[30%] mb-16 sm:mb-0">
		 <img src={"/stats.png"} alt="Statistics" class="w-full" />
	 </div>

		<!-- Philosophy -->
		<div class="w-full pt-0 sm:w-[30%]">
			<h1 class="text-sky-500 font-nunito font-black text-3xl sm:text-5xl text-center m-4">Our Philosophy at LWB Media</h1>
			<p class="text-white text-center text-sm sm:text-xl">
			At LWB Media, we empower influencers to take control of their brand and revenue. Instead of letting other profit from their audience, we help creators build authentic, paid communities that deepen connections and add lasting value. We'd be honored to help you achieve the same success—schedule your free call below 
			</p>
			<span class="flex flex-row justify-center">
				<SpeakToTeamButton />
			</span>
		</div>
	</div>

	<div class="w-full my-[30vh]"></div>

	<!-- Paid Advertising -->
	<div class="text-white w-full flex flex-wrap flex-row justify-evenly">
		<!-- Stats -->
	<div class="w-full sm:w-[30%] mb-16 sm:mb-0">
		<p class="text-white text-md sm:text-2xl">What we offer</p>
		<h1 class="text-sky-500 font-nunito font-black text-3xl sm:text-5xl ml-0 m-4">Paid Communities Tailored To Your Audience</h1>
		<p class="text-white text-sm sm:text-xl">
			We focus on one thing—and we do it better than anyone else. If you're looking for an agency that offers a broad, full-service solution that tries to do everything, but doesn’t really move the needle, then we’re not for you.
			<br />
			<br />
			But if you’re seeking an agency that with just a few clicks is laser-focused on helping you build a paid community that delivers real, tangible results. We’re for you.
		</p>
		<SpeakToTeamButton />
	</div>

	<!-- What we offer -->
	<div class="w-full pt-0 sm:w-[30%]">
		<h1 class="text-sky-500 font-nunito font-black text-xl sm:text-3xl">True Mastery Requires Focus, so…</h1>
		<p class="text-white text-xs sm:text-lg capitalize italic font-thin">
			 We only offer one service
		</p>
		<br>
		<div class="flex flex-col">
			<ul>
				{#each ["Content Creation", "Webdesign", "Social Media Management", "Email Marketing", "PR Service", "Instagram Growth"] as title}
				<li class="flex my-3 text-white font-nunito text-md sm:text-lg align-top">
					<CircleX class="mr-2" color="red" /> 
					{title}
				</li>
				{/each}
			</ul>
		</div>

	</div>
</div>


	<div class="w-full my-[30vh]"></div>

	<!-- Calendly Embed -->
	<CalendlyEmbed url={CALENDLY_LINK} />

	<div class="w-full my-[5vh]"></div>

	<!-- Footer -->
	<div class="w-full flex flex-row justify-center">
		<div class="flex flex-col w-full sm:w-[40vw] text-center content-center">
			<span class="text-sky-500 font-nunito font-black text-2xl sm:text-5xl text-center">Have A General Inquiry?</span>
			<span class="text-white text-lg sm:text-2xl text-center mb-4">If you have a general inquiry and would like to speak to our expert team, you can contact us via email at: logan@lwb-media.com</span>
			<span class="flex flex-row justify-center">
				<SpeakToTeamButton />
			</span>
		</div>
	</div>
</div>
