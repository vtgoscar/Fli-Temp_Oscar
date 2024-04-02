<script>
	import heroImg from '../assets/images/aperl_tp_3.png';
	import Header from '../components/navbar.svelte';
	import About from '../components/about.svelte';
	import Services from '../components/services.svelte';
	import AgencyTab from '../components/agencyTab.svelte';
	import Cta from '../components/cta.svelte';
	import Client from '../components/client.svelte';
	import Pricing from '../components/pricing.svelte';
	import Blogs from '../components/blog.svelte';
	import GetInTouch from '../components/getInTuoch.svelte';
	import Footer from '../components/footer.svelte';
	import Switcher from '../components/switcher.svelte';
	import Modal from '../components/Modal.svelte';

	let loading = false;
	let modalTypeToShow = null;

	function openModal(modalType) {
		console.log('Opening modal:', modalType);
		modalTypeToShow = modalType;
	}
</script>

<Header />

<section
	class="relative overflow-hidden md:py-48 py-40 bg-teal-500/5 dark:bg-teal-500/20"
	id="home"
>
	<div class="container relative mt-8">
		<div class="grid md:grid-cols-2 grid-cols-1 gap-6 items-center">
			<div>
				<h1
					class="font-semibold lg:leading-normal leading-normal tracking-wide text-4xl lg:text-5xl mb-5"
				>
					"Where Disc Golf Takes Flight"
				</h1>
				<p class="text-slate-500 text-lg max-w-xl font-semibold">
					FLI Golf is a gender equal brand supporting gender equality and women's empowerment. Our
					brand is dedicated to uplifting women in sports, particularly within the dynamic world of
					disc golf. Expect nothing but the best from us. Exclusive limited edition clothing and
					apparel drops throughout the year. Player & Brand collaborations. Disc Brand
					collaborations. Always a portion of our proceeds goes towards organizations focusing on
					gender equality and youth sports. <br /><br />We're all about collaboration, whether it's
					partnering with players and brands who share our values or teaming up with top disc
					manufacturers to provide you with the finest equipment for your game. What's more, when
					you support FLI Golf, you're also supporting a greater cause – a portion of our proceeds
					is directed towards organizations championing gender equality in sports and fostering
					youth athletic programs. Join us today to be part of a community that's not just playing
					the game, but changing it for the better.
				</p>
				<div class="mt-6">
					<!-- Button triggering the modal -->
					<button
						type="button"
						class="h-10 px-6 tracking-wide inline-flex items-center justify-center font-medium rounded-md bg-teal-500 text-white"
						on:click={() => openModal('register')}
					>
						Register
					</button>
				</div>
			</div>

			<div class="lg:ms-8">
				<div class="relative">
					<img src={heroImg} class="relative top-16" alt="" />
					<div
						class="overflow-hidden absolute md:size-[500px] size-[400px] bg-gradient-to-tl to-teal-500/20 via-teal-500/70 from-teal-500 bottom-1/2 translate-y-1/2 md:start-0 start-1/2 ltr:md:translate-x-0 ltr:-translate-x-1/2 rtl:md:translate-x-0 rtl:translate-x-1/2 -z-1 shadow-md shadow-teal-500/10 rounded-full"
					/>
				</div>
			</div>
		</div>
	</div>
</section>

<About />
<Services />
<Cta />
<Client />
<Pricing />
<GetInTouch />
<Footer />
<Switcher />

<Modal {modalTypeToShow} />
