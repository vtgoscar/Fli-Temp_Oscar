<script>
	import ctaImage from '../assets/images/home.png';
	import { Modal, Content, Trigger } from 'sv-popup';
</script>

<section class="relative md:py-24 py-16 md:pt-0 pt-0">
	<div class="container relative">
		<div class="grid grid-cols-1 justify-center">
			<div class="relative z-1">
				<div class="grid grid-cols-1 md:text-start text-center justify-center">
					<div class="relative">
						<img src={ctaImage} alt="" />
						<div class="absolute bottom-2/4 translate-y-2/4 start-0 end-0 text-center">
							<Modal>
								<Content>
									<iframe
										width="100%"
										height="480"
										src="https://www.youtube.com/embed/aR3htgTnzRs"
										title="YouTube video player"
										frameborder="0"
										allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
										allowfullscreen
									/>
								</Content>
								<Trigger>
									<a
										class="lightbox size-20 rounded-full shadow-lg dark:shadow-gray-700 inline-flex items-center justify-center bg-white dark:bg-slate-900 text-teal-500 dark:text-white"
									>
										<i class="mdi mdi-play inline-flex items-center justify-center text-2xl" />
									</a>
								</Trigger>
							</Modal>
						</div>
					</div>
				</div>
				<div class="content md:mt-8">
					<div class="grid lg:grid-cols-12 grid-cols-1 md:text-start text-center justify-center">
						<div class="lg:col-start-2 lg:col-span-10">
							<div class="grid md:grid-cols-2 grid-cols-1 items-center" />
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>

	<div
		class="absolute bottom-0 start-0 end-0 sm:h-2/3 h-4/5 bg-gradient-to-b from-teal-400 to-teal-500"
	/>
</section>
