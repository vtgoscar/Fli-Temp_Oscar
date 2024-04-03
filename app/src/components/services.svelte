<script>
	import {
		TrendingUpIcon,
		PauseIcon,
		CompassIcon,
		CommandIcon,
		HexagonIcon,
		MaximizeIcon,
		BellIcon,
		MonitorIcon
	} from 'svelte-feather-icons';

	const servicesData = [
		{
			icon: TrendingUpIcon,
			title: 'Empowering Women',
			desc: 'Ensuring equal pay for women empowers them by recognizing their invaluable contributions and talents on par with men, fostering a more equitable society where individuals are valued based on merit rather than gender.',
			body: 'Empowering women in all aspects of life leads to a more inclusive society. By providing equal opportunities, we foster innovation and creativity, benefiting everyone in the community.',
			link: 'empowering'
		},
		{
			icon: PauseIcon,
			title: 'Gender Equality in Sports',
			desc: 'Gender equality in sports is achieved when athletes of all genders have equal opportunities for participation, access to resources, recognition, and support, creating a level playing field where talent and dedication determine success rather than gender.',
			body: 'Promoting gender equality in sports is not just about fairness; it is about creating a healthier society. When everyone has the chance to compete and excel, we redefine traditional notions of athleticism and inspire future generations.',
			link: 'gender-equality-sports'
		},
		{
			icon: CompassIcon,
			title: 'Limited Edition Clothing Drops',
			desc: 'Limited edition clothing drops offer a unique opportunity for fashion enthusiasts to own exclusive pieces that reflect their individuality and style, fostering a sense of exclusivity and excitement within the fashion community.',
			body: 'Limited edition clothing drops are more than just fashion; they are a form of self-expression. By offering exclusive designs, we celebrate diversity and creativity, allowing individuals to showcase their unique tastes.',
			link: 'limited-edition-clothing-drops'
		},
		{
			icon: CommandIcon,
			title: 'Collaborations',
			desc: 'In our collaborative efforts, we partner with like-minded organizations and individuals to drive positive change and innovation in disc golf. Through shared visions and combined expertise, we aim to create impactful projects, events, and initiatives that benefit the entire disc golf community.',
			body: 'Collaboration is key to success in any endeavor. By working together, we pool resources, share knowledge, and achieve greater results than we could alone. Our partnerships drive innovation and inspire positive change.',
			link: 'collaborations'
		},
		{
			icon: HexagonIcon,
			title: 'FAQ',
			desc: 'Is disc golf popular enough as a sport to sustain a tournament of this magnitude? A) There are over 51.6 MILLION registered rounds of disc golf played each year worldwide. (As per sportspromedia.com and udisc.com)',
			body: 'How accessible is Disc Golf to the average American? A) 500 MILLION people live within 6 miles of a disc golf course.',
			link: 'competition'
		},
		{
			icon: MaximizeIcon,
			title: 'About',
			desc: 'The management team of FLI Golf has years of experience in the sports, entertainment, and business management industries, which has allowed FLI Golf to secure a major production partner, ensuring live play media coverage',
			body: 'Our team is passionate about revolutionizing the world of disc golf. With expertise in sports, entertainment, and business management, we are dedicated to providing top-notch experiences for players and fans alike.',
			link: 'about'
		},
		{
			icon: BellIcon,
			title: 'Social Media',
			desc: "In disc golf social media, we amplify community voices, foster connections, and promote the sport's spirit. Join us in shaping an inclusive space for enthusiasts to share, celebrate, and evolve disc golf culture.",
			body: 'Social media has become a powerful tool for connecting disc golf enthusiasts worldwide. Through our platforms, we amplify diverse voices, share stories, and foster a sense of community that transcends geographical boundaries.',
			link: 'social-media'
		},
		{
			icon: MonitorIcon,
			title: 'Subscriptions',
			desc: 'Enjoy a wide range of perks including early access to drops, exclusive discounts, podcast subscriptions, limited edition apparel, and much more.',
			body: 'Unlock a world of exclusive benefits with FLI Golf. Gain early access to our latest drops, ensuring you never miss out on the hottest releases. Enjoy exclusive discounts on our premium apparel, designed to elevate your style both on and off the course. Dive into our curated podcast content, covering everything from expert tips to inspiring stories within the world of disc golf. Plus, indulge in our collection of limited edition apparel, meticulously crafted to showcase your passion for the sport. Join us today and experience a community dedicated to enhancing your disc golf journey with perks tailored just for you.',
			link: 'design-branding'
		}
	];

	let showModal = false;
	let activeService = {};

	function openModal(service) {
		activeService = service;
		showModal = true;
	}

	function closeModal() {
		activeService = {};
		showModal = false;
	}
</script>

<section class="relative md:py-24 py-16 bg-slate-50 dark:bg-slate-800" id="services">
	<div class="container relative">
		<div class="grid grid-cols-1 pb-6 text-center">
			<h3 class="font-semibold text-2xl leading-normal mb-4">Info</h3>
			<p class="text-slate-400 font-semibold max-w-xl mx-auto">
				Equality isn't just a goal – it's a fundamental value we uphold in everything we do. We're
				committed to breaking down gender barriers and promoting equality in disc golf and beyond.
			</p>
		</div>

		<div class="grid lg:grid-cols-4 md:grid-cols-2 sm:grid-cols-2 grid-cols-1 gap-6 mt-6">
			{#each servicesData as item}
				{@const Icon = item.icon}
				<div
					class="group rounded-md shadow dark:shadow-gray-700 relative bg-white dark:bg-slate-900 p-6 overflow-hidden h-fit"
				>
					<div
						class="flex items-center justify-center size-14 -rotate-45 bg-gradient-to-r from-transparent to-teal-500/10 text-teal-500 text-center rounded-full group-hover:bg-teal-500/10 duration-500"
					>
						<Icon class="size-6 rotate-45" />
					</div>
					<div class="content mt-6 relative z-1">
						<a
							href="#"
							on:click|preventDefault={() => openModal(item)}
							class="title text-lg font-semibold hover:text-teal-500">{item.title}</a
						>
						<p class="text-slate-400 mt-3">{item.desc}</p>
						<div class="mt-6">
							<a href="#" on:click|preventDefault={() => openModal(item)} class="text-teal-500"
								>Read More <i class="mdi mdi-chevron-right align-middle" /></a
							>
						</div>
					</div>
					<div class="absolute bottom-0 -end-16">
						<Icon
							class="size-48 text-teal-500 opacity-[0.04] dark:opacity-[0.04] group-hover:opacity-10 duration-500"
						/>
					</div>
				</div>
			{/each}
		</div>
	</div>

	{#if showModal}
		<div class="fixed inset-0 z-50 flex items-center justify-center bg-black bg-opacity-50">
			<div class="bg-white p-6 rounded-lg shadow-lg max-w-md">
				<h2 class="text-gray-700 text-xl font-semibold mb-4">{activeService.title}</h2>
				<p class="text-gray-700">{activeService.desc}</p>
				<br />
				<p class="text-gray-700">{activeService.body}</p>
				<button
					class="mt-4 px-4 py-2 bg-teal-500 text-white rounded hover:bg-teal-600"
					on:click={closeModal}>Close</button
				>
			</div>
		</div>
	{/if}
</section>
