<script>
    import { Modal, Content, Trigger } from "sv-popup";
	import Counter from "../../../components/counter.svelte";
	import heroImg from "../../../assets/images/about2.jpg"
	import bg from '../../../assets/images/bg/2.png';
	import {MonitorIcon} from 'svelte-feather-icons'
</script>
<Counter />
<section class="relative flex items-center md:h-screen py-36 bg-no-repeat bg-center bg-cover" id="home" style:background-image="url({bg})">
	<div class="container relative">
		<div class="grid lg:grid-cols-12 md:grid-cols-2 grid-cols-1 items-center mt-6 gap-6 relative">
			<div class="lg:col-span-7 md:me-6">
				<h4 class="font-semibold lg:leading-normal leading-normal tracking-wide text-4xl lg:text-5xl mb-5">Revolutionizing Your <span class="text-teal-500 font-bold">Business</span> with Upcover</h4>
				<p class="text-slate-400 text-lg max-w-xl">This is just a simple text made for this unique and awesome template, you can replace it with any text.</p>
			
				<div class="relative mt-6 space-x-1">
					<a href="/" class="h-10 px-6 tracking-wide inline-flex items-center justify-center font-medium rounded-md bg-teal-500 text-white">Get Started</a>
					<Modal>
						<Content>
						  <iframe
							src="https://www.youtube.com/embed/S_CGed6E610"
							title="YouTube video player"
							frameborder="0"
							allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
							allowfullscreen
							style="width: 100%;aspect-ratio: 16/9;height: auto;"
						  />
						</Content>
						<Trigger>
							<a  class="size-9 inline-flex items-center justify-center tracking-wide align-middle duration-500 text-base text-center bg-teal-500 text-white rounded-full lightbox"><i class="mdi mdi-play text-xl align-middle"></i></a><small class="text-sm font-medium uppercase align-middle ms-2">Watch Now</small>
						</Trigger>
					  </Modal>
				</div>
			</div>

			<div class="lg:col-span-5">
				<div class="relative">
					<img src={heroImg} class="mx-auto rounded-[150px] rounded-br-2xl shadow dark:shadow-gray-700 w-[90%]" alt=""/>

					<div class="overflow-hidden after:content-[''] after:absolute after:h-10 after:w-10 after:bg-teal-500/20 after:top-0 after:start-0 after:-z-1 after:rounded-lg after:animate-[spin_10s_linear_infinite]"></div>
				
					<div class="absolute flex justify-between items-center bottom-16 md:-start-10 -start-5 p-4 rounded-lg shadow-md dark:shadow-gray-800 bg-white dark:bg-slate-900 w-60 m-3">
						<div class="flex items-center">
							<div class="flex items-center justify-center h-[65px] min-w-[65px] bg-teal-500/5 text-teal-500 text-center rounded-full me-3">
								<MonitorIcon class="h-6 w-6"/>
							</div>
							<div class="flex-1">
								<span class="text-slate-400">Visitor</span>
								<p class="text-xl font-bold">
									<span class="counter-value" data-target="4589">0</span></p>
							</div>
						</div>

						<span class="text-red-600"><i class="uil uil-chart-down"></i> 0.5%</span>
					</div>

					<div class="absolute top-16 md:-end-10 -end-5 p-4 rounded-lg shadow-md dark:shadow-gray-800 bg-white dark:bg-slate-900 w-48 m-3">
						<h5 class="text-lg font-semibold mb-3">Manage Software</h5>
						<div class="flex justify-between mt-3 mb-2">
							<span class="text-slate-400">Progress</span>
							<span class="text-slate-400">84%</span>
						</div>
						<div class="w-full bg-gray-100 dark:bg-gray-800 rounded-full h-[6px]">
							<div class="bg-teal-500 h-[6px] rounded-full" style="width: 84%"></div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>