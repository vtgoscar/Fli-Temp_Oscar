<script>
    import hero1 from "../../../assets/images/ab1.jpg";
	import hero2 from "../../../assets/images/ab3.jpg";
	import hero3 from "../../../assets/images/ab4.jpg";
	import hero4 from "../../../assets/images/ab7.jpg";
	import hero5 from "../../../assets/images/ab6.jpg";
	import hero6 from "../../../assets/images/ab5.jpg";
	import hero7 from "../../../assets/images/about2.jpg";
	import company1 from '../../../assets/images/team/amazon.svg';
	import company2 from '../../../assets/images/team/google.svg';
	import company3 from '../../../assets/images/team/lenovo.svg';
	import company4 from '../../../assets/images/team/paypal.svg';
	import company5 from '../../../assets/images/team/shopify.svg';
	import company6 from '../../../assets/images/team/spotify.svg';
	const companyLogo = [company1, company2, company3, company4, company5, company6];
</script>
<section class="relative md:pt-44 py-36 bg-slate-50 dark:bg-slate-800" id="home">
	<div class="container relative">
		<div class="grid grid-cols-1 justify-center text-center">
			<div class="">
				<h1 class="font-bold lg:leading-normal leading-normal tracking-wide text-4xl lg:text-5xl capitalize mb-5">Grow Sales with Our <br/> Strategy First Approach</h1>
				<p class="text-slate-400 text-lg max-w-xl mx-auto">This is just a simple text made for this unique and awesome template, you can replace it with any text.</p>
			
				<div class="subcribe-form mt-6 mb-3">
					<form class="relative max-w-xl mx-auto">
						<input type="email" id="emailid" name="email" class="py-4 pe-40 ps-6 w-full h-[50px] outline-none text-black dark:text-white rounded-full bg-white/60 dark:bg-slate-900/60 shadow dark:shadow-gray-800" placeholder="yourname@domain.com"/>
						<button type="submit" class="px-6 tracking-wide inline-flex items-center justify-center font-medium absolute top-[2px] end-[3px] h-[46px] bg-teal-500 text-white rounded-full">Subscribe Now</button>
					</form>
				</div>

				<span class="font-medium">Looking for help? <a href="/" class="text-teal-500">Get in touch with us</a></span>
			</div>

			<div class="grid lg:grid-cols-12 md:grid-cols-3 grid-cols-1 lg:gap-4 gap-2 mx-auto mt-8 items-center">
				<div class="lg:col-span-4">
					<div class="grid grid-cols-2 gap-4 items-center">
						<div class="">
							<div class="grid grid-cols-1 gap-4">
								<img src={hero1} class="shadow rounded-lg" alt=""/>
							</div>
						</div>

						<div class="">
							<div class="grid grid-cols-1 gap-4">
								<img src={hero2} class="shadow rounded-lg" alt=""/>
								<img src={hero3} class="shadow rounded-lg" alt=""/>
							</div>
						</div>
					</div>
				</div>

				<div class="lg:col-span-4">
					<img src={hero4} class="shadow rounded-lg" alt=""/>
				</div>

				<div class="lg:col-span-4">
					<div class="grid grid-cols-2 gap-4 items-center">
						<div class="">
							<div class="grid grid-cols-1 gap-4">
								<img src={hero5} class="shadow rounded-lg" alt=""/>
								<img src={hero6} class="shadow rounded-lg" alt=""/>
							</div>
						</div>

						<div class="">
							<div class="grid grid-cols-1 gap-4">
								<img src={hero7} class="shadow rounded-lg" alt=""/>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>
<section class="py-6 border-b border-gray-100 dark:border-gray-700">
	<div class="container relative">
		<div class="grid md:grid-cols-6 grid-cols-2 justify-center gap-[30px]">
			{#each companyLogo as item}
				<div class="mx-auto py-4">
					<img src={item} class="h-6" alt=""/>
				</div>
			{/each}
		</div>
	</div>
</section>