<script lang="ts">
	import { onMount } from 'svelte';
	import { supabase } from '/src/suprabaseClient.ts';
	import type { AuthSession } from '@supabase/supabase-js';
	import Account from '$lib/Account.svelte';
	import Auth from '$lib/Auth.svelte';
	import HeroCard from '$lib/components/HeroCard.svelte';

	let session: AuthSession;

	onMount(() => {
		supabase.auth.getSession().then(({ data }) => {
			session = data.session;
		});

		supabase.auth.onAuthStateChange((_event, _session) => {
			session = _session;
		});
	});
</script>

<div class="container mx-auto px-4">
	<!-- HeroCards -->
	<div class="flex justify-between">
		<!-- Existing card -->
		<div class="mt-8">
			<div class="card flex-1 h-144 bg-base-100 shadow-xl overflow-auto mr-4 ring-slate-200">
				<div class="card-body">
					<h2
						class="mt-6 mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white ml-4"
					>
						<div class="badge-large badge badge-secondary blinking">Sign Up NOW</div>
					</h2>
					<a href="#">
						<h5 class="mb-2 text-4xl font-bold text-gray-900 dark:text-white ml-4">
							Be among the exclusive few to get your hands on our first-ever limited edition
							clothing line! Designed with passion and crafted with precision, these pieces are the
							epitome of style and exclusivity.
						</h5>
					</a>
					<a
						href="#"
						class="mb-8 ml-6 inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-green-700 rounded-lg hover:bg-green-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
					>
						Sign up
						<svg
							class="rtl:rotate-180 w-3.5 h-3.5 ms-2"
							aria-hidden="true"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 14 10"
						>
							<path
								stroke="currentColor"
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M1 5h12m0 0L9 1m4 4L9 9"
							/>
						</svg>
					</a>
				</div>
			</div>
		</div>

		<!-- New card -->
		<div class="mt-8">
			<div class="card w-64 h-144 bg-green-500 rounded-lg shadow-xl overflow-auto ring-slate-200">
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
</div>
