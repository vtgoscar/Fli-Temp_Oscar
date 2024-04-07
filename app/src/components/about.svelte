<script>
	import groupImage from '../assets/images/group-fli-1.jpg';
	import Counter from './counter.svelte';
</script>

<Counter />
<section class="relative md:py-24 py-16" id="about">
	<div class="container relative">
		<div class="grid md:grid-cols-12 grid-cols-1 items-center gap-6">
			<div class="md:col-span-6">
				<div class="lg:me-8">
					<figure class="relative">
						<img src={groupImage} class="rounded-full shadow dark:shadow-gray-700" alt="" />
						<figcaption style="text-align: center;">
							Andrew Panza, Dustin Dinsmore, Tony Smart, Mark Colemann and Corey LaRusso
						</figcaption>
					</figure>
				</div>
			</div>

			<div class="md:col-span-6">
				<div class="lg:ms-8">
					<h3 class="font-semibold text-2xl leading-normal mb-4">
						Our Mission: <br /> Redefine Disc Golf
					</h3>

					<p class="text-slate-500 max-w-xl mb-6 font-semibold">
						Our mission is clear and resolute: to redefine the disc golf experience while
						championing inclusivity, empowerment, and equality. Beyond merely a game, disc golf
						serves as our platform for progress, a catalyst for change, and a vibrant community
						united by passion.
					</p>
				</div>
			</div>
		</div>
	</div>
</section>

<style>
</style>
