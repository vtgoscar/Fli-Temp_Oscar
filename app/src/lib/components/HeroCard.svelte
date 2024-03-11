<div class="flex">
	<!-- Existing card -->
	<div class="mt-8">
		<div class="card flex-1 h-144 bg-base-100 shadow-xl overflow-auto mr-4 ring-slate-200">
			<div class="card-body">
				<h2 class="mt-6 mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white ml-4">
					<div class="badge-large badge badge-secondary blinking">Sign Up NOW</div>
				</h2>
				<a href="#">
					<h5 class="mb-2 text-4xl font-bold text-gray-900 dark:text-white ml-4">
						Be among the exclusive few to get your hands on our first-ever limited edition clothing
						line! Designed with passion and crafted with precision, these pieces are the epitome of
						style and exclusivity.
					</h5>
				</a>
				<button
					class="btn btn-lg bg-green-700 text-white px-6 py-3 mt-4 hover:bg-green-800 hover:text-white rounded-full mb-8"
				>
					Sign up
				</button>
			</div>
		</div>
	</div>

	<!-- New card -->
	<div class="mt-8">
		<div class="card w-30 h-144 bg-green-500 rounded-lg shadow-xl overflow-auto ring-slate-200">
			<div class="card-body flex flex-col justify-center items-center text-white">
				<h2 class="mt-8 mb-6 badge-large badge badge-secondary blinking">Subscribe Now</h2>
				<p class="text-center mb-2 text-4xl font-bold text-gray-900 dark:text-white ml-4">
					Get ready for exclusive offers on our first limited edition clothing drop!
				</p>
				<button
					class="btn btn-lg bg-green-700 text-white px-6 py-3 mt-4 hover:bg-green-800 hover:text-white rounded-full mb-8"
				>
					Subscribe
				</button>
			</div>
		</div>
	</div>
</div>

<style>
	@keyframes blink {
		0% {
			color: green;
		}
		50% {
			color: yellow;
		}
		100% {
			color: green;
		}
	}

	.blinking {
		animation: blink 2s infinite;
	}

	.flashing {
		animation: flash 1s infinite;
	}

	.badge-large {
		font-size: 56px; /* Adjust the font size as needed */
	}
</style>
