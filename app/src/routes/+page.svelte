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

<div class="container h-full mx-auto relative">
    <HeroCard class="absolute top-0 left-0 right-0 z-10 mt-16" />
    <div class="space-y-10 text-center flex flex-col items-center relative z-0">
        <!-- Login -->
        <div class="container" style="padding: 50px 0 100px 0">
            {#if !session}
                <Auth />
            {:else}
                <Account {session} />
            {/if}
        </div>
    </div>
</div>
