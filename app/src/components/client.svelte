<script>
	import { Splide, SplideSlide } from '@splidejs/svelte-splide';
	import '@splidejs/svelte-splide/css';
	// or only core styles
	import '@splidejs/svelte-splide/css/core';
	import client1 from '../assets/images/team/ap_1_bk.jpg';
	import client2 from '../assets/images/team/dd_1_bk.jpg';
	import client3 from '../assets/images/team/ts_1_bk.jpg';
	import client4 from '../assets/images/team/mc_1_bk.jpg';
	import client5 from '../assets/images/team/cl_1_bk.jpg';
	import client6 from '../assets/images/team/06.jpg';

	const clientData = [
		{
			image: client1,
			name: 'Andrew Panza',
			title: 'CEO / Co-Founder',
			desc: '" As the son of a two-sport college athlete mother and with three athletic sisters, I have witnessed firsthand the limited opportunities women face in professional sports. Inspired by their passion and talent, I am launching a gender-equal disc golf brand to pave the way for future generations, ensuring that all athletes have equal opportunities to pursue their dreams. "'
		},
		{
			image: client2,
			name: 'Dustin Dinsmore',
			title: 'CTO / Co-Founder',
			desc: '" As someone deeply ingrained in the world of sports and leveraging my background in technology, I am committed to promoting gender equality in sports. Together, let us harness the power of innovation and inclusivity to create a level playing field for all athletes." "'
		},
		{
			image: client3,
			name: 'Tony Smart',
			title: 'President',
			desc: '" As a 100% disabled Marine Corps veteran, I am proud to stand beside the men and women who served our great country. As the President of FLI Golf, I am equally as honored to be a part of a movement in sports that can bring a positive future to our young men and women."'
		},
		{
			image: client4,
			name: 'Mark Coleman',
			title: 'Production Director',
			desc: '" Thus, Lorem Ipsum has only limited suitability as a visual filler for German texts "'
		},
		{
			image: client5,
			name: 'Corey La Russo',
			title: 'Chief Marketing Officer',
			desc: '" There is now an abundance of readable dummy texts. These are usually used when a text is required"'
		},
		{
			image: client6,
			name: 'Jim Neely',
			title: 'Live Production Director',
			desc: '" According to most sources, Lorum Ipsum can be traced back to a text composed by Cicero "'
		}
	];

	const settings = {
		container: '.tiny-three-item',
		controls: false,
		mouseDrag: true,
		loop: true,
		rewind: true,
		autoplay: true,
		autoplayButtonOutput: false,
		autoplayTimeout: 3000,
		speed: 400,
		gutter: 12,
		perPage: 3,
		arrows: false,
		breakpoints: {
			992: {
				perPage: 3
			},

			767: {
				perPage: 2
			},

			320: {
				perPage: 1
			}
		}
	};
</script>

<section class="relative md:py-24 py-16" id="review">
	5t5
	<div class="container relative">
		<div class="grid grid-cols-1 pb-6 text-center">
			<h3 class="font-semibold text-2xl leading-normal mb-4">Managment Testimonials</h3>

			<p class="text-slate-400 max-w-xl mx-auto">
				Below are testimonials from the FLI Golf Co-Founders and Management Team!
			</p>
		</div>

		<div class="grid grid-cols-1 mt-6">
			<div class="tiny-three-item">
				<Splide aria-label="My Favorite Images" options={settings}>
					{#each clientData as item}
						<SplideSlide>
							<div class="tiny-slide text-center">
								<div class="cursor-e-resize">
									<div
										class="content relative rounded shadow dark:shadow-gray-700 m-2 p-6 bg-white dark:bg-slate-900 before:content-[''] before:absolute before:start-1/2 before:-bottom-[4px] before:box-border before:border-8 before:rotate-[45deg] before:border-t-transparent before:border-e-white dark:before:border-e-slate-900 before:border-b-white dark:before:border-b-slate-900 before:border-s-transparent before:shadow-testi dark:before:shadow-gray-700 before:origin-top-left"
									>
										<i class="mdi mdi-format-quote-open mdi-48px text-teal-500" />
										<p class="text-slate-400">{item.desc}</p>
										<ul class="list-none mb-0 text-amber-400 mt-3">
											<li class="inline"><i class="mdi mdi-star" /></li>
											<li class="inline"><i class="mdi mdi-star" /></li>
											<li class="inline"><i class="mdi mdi-star" /></li>
											<li class="inline"><i class="mdi mdi-star" /></li>
											<li class="inline"><i class="mdi mdi-star" /></li>
										</ul>
									</div>

									<div class="text-center mt-5">
										<img
											src={item.image}
											class="size-14 rounded-full shadow-md dark:shadow-gray-700 mx-auto"
											alt=""
										/>
										<h6 class="mt-2 font-semibold">{item.name}</h6>
										<span class="text-slate-400 text-sm">{item.title}</span>
									</div>
								</div>
							</div>
						</SplideSlide>
					{/each}
				</Splide>
			</div>
		</div>
	</div>
</section>
