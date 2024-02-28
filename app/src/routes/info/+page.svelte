<script lang="ts">
	import Icon from '@iconify/svelte';
	// Any JavaScript can go here, e.g., dynamic behavior or data handling
	let listItems = [
		'Pairs Competition: FLI GOLF TOUR sets a new standard, spotlighting mixed-gender teams — a nod to both talent amalgamation and a commitment to championing gender equality.',
		'Monthly Tournaments: Anchoring the tour are its monthly 1-day events, hosted at various renowned college campuses throughout the U.S.',
		'Custom Course Excellence: Every tournament showcases a meticulously designed course, pushing players to their limits and ensuring fans are on the edge of their seats.',
		"Uplift Disc Golf: Elevate the sport's stature, broadening its fan base and affirming its competitive essence.",
		'Promote Gender Equality: Pioneering mixed-gender competitions, the tour positions itself at the forefront of inclusivity in sports.',
		'Entertainment First: A commitment to offering fans a captivating experience, ensuring they are as much a part of the tour as the athletes.',
		'Inspire Future Talents: Showcase the zenith of disc golf skill, aiming to kindle passion in the upcoming generation.',
		'Sponsorships: Collaborations with eminent brands across various sectors form a significant chunk of the revenue.',
		'Ticketing: With multiple ticket options, fans can enjoy the interactive center on media day, tournament play, and even a live show to culminate the event.',
		'Merchandising: The tour boosts its earnings with a diverse range of official merchandise, including branded attire and exclusive collectibles.',
		'Legal Gambling Partnerships: Tournaments are amplified by alliances with authorized sportsbooks, introducing a thrilling dimension for fans.',
		'Media Collaborations: Venturing into broadcasting and streaming tie-ups not only enhances visibility but opens up monetization avenues.'
	];
</script>

<div>
	<img src="/GROUP.jpg" alt="Group Image" />
	<div class="image-caption mb-6">
		Andrew Panza, Dustin Dinsmore, Tony Smart, Mark Colemann and Corey LaRusso
	</div>
</div>

<div class="container mx-auto px-4 py-8">
	<h1 class="text-3xl font-bold mb-4">Welcome to FLI Golf: Where Tradition Meets Collaboration</h1>
	<p class="text-lg mb-6">
		At FLI Golf, we're more than just a brand – we're a movement dedicated to revolutionizing the
		world of disc golf while championing values of empowerment and equality. As a newcomer to the
		scene, we're proud to represent the spirit of the sport and advocate for positive change.
	</p>

	<h2 class="text-2xl font-bold mb-2">Our Mission: Redefining Disc Golf with Purpose</h2>
	<p class="text-lg mb-6">
		At FLI Golf, our mission is simple yet profound: to redefine the disc golf experience while
		fostering a culture of inclusivity, empowerment, and equality. Disc golf isn't just a game to us
		– it's a platform for progress, a catalyst for change, and a community united by passion.
	</p>

	<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
		<div class="bg-green-700 text-white p-4 rounded-lg">
			<h3 class="text-xl font-bold mb-2">Empowering Women</h3>
			<p class="text-lg">
				We believe in the power of representation and diversity. That's why we're dedicated to
				empowering women in disc golf, creating opportunities for growth, leadership, and
				recognition within the sport.
			</p>
		</div>
		<div class="bg-green-700 text-white p-4 rounded-lg">
			<h3 class="text-xl font-bold mb-2">Gender Equality in Sports</h3>
			<p class="text-lg">
				Equality isn't just a goal – it's a fundamental value we uphold in everything we do. We're
				committed to breaking down gender barriers and promoting equality in disc golf and beyond.
			</p>
		</div>
		<div class="bg-green-700 text-white p-4 rounded-lg">
			<h3 class="text-xl font-bold mb-2">Limited Edition Clothing Drops and Collaborations</h3>
			<p class="text-lg">
				FLI Golf isn't just about discs – it's a lifestyle. Stay ahead of the curve with our
				exclusive clothing drops and collaborations with like-minded brands. From limited edition
				apparel to exciting partnerships, we're always pushing the boundaries of style and
				innovation.
			</p>
		</div>
	</div>

	<h2 class="text-2xl font-bold mt-8 mb-2">Join the FLI Golf Movement</h2>
	<p class="text-lg mb-6">
		Whether you're a seasoned veteran or a curious newcomer, FLI Golf welcomes you with open arms.
		Together, we can push the boundaries, challenge the status quo, and make a positive impact on
		the world of disc golf.
	</p>

	<p class="text-lg mb-6">
		Ready to join the FLI Golf movement? Explore our products, connect with our community, and
		experience the difference of disc golf with FLI Golf by your side. Together, let's fly higher,
		play better, and change the game for good.
	</p>
</div>

<div class="p-6 text-white">
	<p class="text-xl font-semibold mb-4">
		Located at the intersection of sports and entertainment, the FLI GOLF TOUR - Pairs Edition is
		all set to mark a new chapter in the world of disc golf.
	</p>
	<div class="border-t pt-4 mt-4">
		<p class="text-lg mb-2">For media inquiries, please contact:</p>
		<div class="flex items-center">
			<Icon icon="ion:mail-outline" class="mr-2" />
			<a href="mailto:info@fligolf.com" class="text-blue-600 underline">info@fligolf.com</a>
		</div>
	</div>
</div>

<style>
	.customBulletList {
		list-style-type: none;
		padding-left: 0;
	}

	.customBulletList li {
		position: relative;
		padding-left: 30px; /* Adjust depending on the size of your image */
		margin-bottom: 10px;
	}

	.customBulletList li::before {
		content: '';
		position: absolute;
		left: 0;
		top: 50%;
		transform: translateY(-50%);
		width: 20px; /* Adjust based on the actual size of your image */
		height: 20px; /* Adjust based on the actual size of your image */
		background-image: url('/FLI_BULLET.png');
		background-size: cover;
		background-repeat: no-repeat;
	}
</style>
