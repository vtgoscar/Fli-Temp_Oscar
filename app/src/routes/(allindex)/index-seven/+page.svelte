<script>
  	import bg from '../../../assets/images/bg/1.jpg'
	import bg2 from '../../../assets/images/bg/2.jpg';
	import { Splide, SplideSlide,SplideTrack } from '@splidejs/svelte-splide';
	const options = {
    rewind  : true,
    autoplay: true,
    arrows  : true,
  }
  
</script>

<section class="swiper-slider-hero relative block h-screen" id="home">
	<div class="swiper-container absolute end-0 top-0 w-full h-full">
		<Splide   options={ {
			rewind: true,
			autoplay : true,
			type  : 'fade',
			interval : 2000,
			classes: {
				// pagination: ' splide__pagination__page swiper-pagination swiper-pagination-clickable swiper-pagination-bullets',
		page      : 'splide__pagination__page swiper-pagination-bullet',
  },
		  } } hasTrack={ false } class="h-screen w-full h-full" autoPlay={true} infiniteLoop={true} interval={2000} showStatus={false} showThumbs={false} showArrows={false} aria-labelledby="autoplay-example-heading">
			<SplideTrack>
			<SplideSlide class="swiper-slide flex items-center overflow-hidden w-full h-full">
				<div class="slide-inner absolute end-0 top-0 w-full h-full slide-bg-image flex items-center bg-center;" style:background-image="url({bg})">
					<div class="absolute inset-0 bg-black/70"></div>
					<div class="container relative">
						<div class="grid grid-cols-1">
							<div class="text-left">
								<h1 class="font-bold lg:leading-normal leading-normal tracking-wide text-4xl lg:text-5xl capitalize text-white mb-5">Connect with <br/> customers smartly</h1>
								<p class="text-white/70 text-lg max-w-xl">This is just a simple text made for this unique and awesome template, you can replace it with any text.</p>
								
								<div class="mt-6">
									<a href="/" class="h-10 px-6 tracking-wide inline-flex items-center justify-center font-medium rounded-md bg-teal-500 text-white">See More</a>
								</div>
							</div>
						</div>
					</div>
				</div>
			</SplideSlide> 

			<SplideSlide class="swiper-slide flex items-center overflow-hidden w-full h-full">
				<div class="slide-inner absolute end-0 top-0 w-full h-full slide-bg-image flex items-center bg-center;" style:background-image="url({bg2})">
					<div class="absolute inset-0 bg-black/70"></div>
					<div class="container relative">
						<div class="grid grid-cols-1">
							<div class="text-left">
								<h1 class="font-bold lg:leading-normal leading-normal tracking-wide text-4xl lg:text-5xl capitalize text-white mb-5">Get all the <br/> inspirations for your business</h1>
								<p class="text-white/70 text-lg max-w-xl">This is just a simple text made for this unique and awesome template, you can replace it with any text.</p>
								
								<div class="mt-6">
									<a href="/" class="h-10 px-6 tracking-wide inline-flex items-center justify-center font-medium rounded-md bg-teal-500 text-white">See More</a>
								</div>
							</div>
						</div>
					</div>
				</div>
			</SplideSlide> 
		</SplideTrack>
			<div class="splide__arrows">
				<div class="splide__arrow splide__arrow--prev swiper-button-prev bg-transparent w-[35px] h-[35px] leading-[35px] -mt-[30px] bg-none border border-solid border-white/50 text-white hover:bg-teal-500 rounded-full text-center" tabindex="0" role="button" aria-label="Previous slide"></div>
				<div class="splide__arrow splide__arrow--next swiper-button-next bg-transparent w-[35px] h-[35px] leading-[35px] -mt-[30px] bg-none border border-solid border-white/50 text-white hover:bg-teal-500 rounded-full text-center" tabindex="0" role="button" aria-label="Next slide"></div>
			  </div>
		</Splide>

	</div>
</section>