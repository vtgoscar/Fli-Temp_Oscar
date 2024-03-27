<script>
	import obj1 from '../assets/images/objectives/streaming.webp';
	import obj2 from '../assets/images/objectives/design.webp';
	import obj3 from '../assets/images/objectives/reward.webp';
	let activeIndex = 1;
</script>

<section class="realtive md:py-24 py-16">
	<div class="container relative">
		<div class="grid grid-cols-1 pb-6 text-center">
			<h3 class="font-semibold text-2xl leading-normal mb-4">FLI Golf Business Objectives</h3>
			<p class="text-slate-400 max-w-xl mx-auto">
				The sport of disc golf is already available for live betting options via crypto currency and
				crypto platforms. Communication platforms such as discord will be key to capturing this
				community of fans.
			</p>
		</div>

		<div class="grid md:grid-cols-12 grid-cols-1 mt-6 gap-6">
			<div class="lg:col-span-4 md:col-span-5">
				<div class="sticky top-20">
					<ul
						class="flex-column p-6 bg-white dark:bg-slate-900 shadow dark:shadow-gray-700 rounded-md"
					>
						<li role="presentation">
							<button
								class={`px-4 py-2 text-start text-base font-medium rounded-md w-full hover:text-teal-500 duration-500 ${
									activeIndex === 1 ? 'text-white bg-teal-500 hover:text-white' : ''
								}`}
								on:click={() => (activeIndex = 1)}
							>
								<span class="block">FLI Golf</span>
								<span class="text-lg mt-2 block">Streamed on a major sports platform</span>
								<span class="block mt-2">Hosting the top players in the world</span>
							</button>
						</li>
						<li role="presentation">
							<button
								class={`px-4 py-2 text-start text-base font-medium rounded-md w-full mt-6 hover:text-teal-500 duration-500 ${
									activeIndex === 2 ? 'text-white bg-teal-500 hover:text-white' : ''
								}`}
								on:click={() => (activeIndex = 2)}
							>
								<span class="block">Unique Course Design</span>
								<span class="text-lg mt-2 block"
									>Our disc golf courses are renowned for their innovative and captivating designs.
								</span>
								<span class="block mt-2"
									>Our courses offer a diverse range of challenges to test players of all skill
									levels.</span
								>
							</button>
						</li>
						<li role="presentation">
							<button
								class={`px-4 py-2 text-start text-base font-medium rounded-md w-full mt-6 hover:text-teal-500 duration-500 ${
									activeIndex === 3 ? 'text-white bg-teal-500 hover:text-white' : ''
								}`}
								on:click={() => (activeIndex = 3)}
							>
								<span class="block">Provide our partners, advertising, and sponsors</span>
								<span class="text-lg mt-2 block">Results & Reporting</span>
								<span class="block mt-2"
									>We offer exciting venue and marketing platform where they can receive proper
									compensation for their financial commitments</span
								>
							</button>
						</li>
					</ul>
				</div>
			</div>

			<div class="lg:col-span-8 md:col-span-7">
				<div
					id="myTabContent"
					class="p-6 bg-white dark:bg-slate-900 shadow dark:shadow-gray-700 rounded-md"
				>
					<div class={activeIndex === 1 ? '' : 'hidden'}>
						<img src={obj1} class="shadow dark:shadow-gray-700 rounded-md" alt="" />

						<div class="mt-6">
							<h5 class="text-lg font-medium">Live Streaming</h5>
							<p class="text-slate-400 mt-4">View live streaming durring our events.</p>
							<div class="mt-4">
								<a href="/" class="text-teal-500"
									>Read More <i class="mdi mdi-chevron-right align-middle" /></a
								>
							</div>
						</div>
					</div>
					<div class={activeIndex === 2 ? '' : 'hidden'}>
						<img src={obj2} class="shadow dark:shadow-gray-700 rounded-md" alt="" />

						<div class="mt-6">
							<h5 class="text-lg font-medium">Strategic Design Elements</h5>
							<p class="text-slate-400 mt-4">
								We strategically place obstacles, such as trees, bushes, and water hazards, to add
								strategic depth to each hole. Thoughtful placement of these elements encourages
								players to develop creative shot-making skills and strategic decision-making.
							</p>
							<div class="mt-4">
								<a href="/" class="text-teal-500"
									>Read More <i class="mdi mdi-chevron-right align-middle" /></a
								>
							</div>
						</div>
					</div>
					<div class={activeIndex === 3 ? '' : 'hidden'}>
						<img src={obj3} class="shadow dark:shadow-gray-700 rounded-md" alt="" />

						<div class="mt-6">
							<h5 class="text-lg font-medium">Results & Reporting</h5>
							<p class="text-slate-400 mt-4">
								Lorem ipsum dolor sit amet, consectetur adipisicing elit. Itaque, impedit vitae.
								Nobis, similique omnis cumque sapiente laboriosam animi quod cupiditate?
							</p>
							<div class="mt-4">
								<a href="/" class="text-teal-500"
									>Read More <i class="mdi mdi-chevron-right align-middle" /></a
								>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>
