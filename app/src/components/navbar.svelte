<script lang="ts">
    import { onMount } from 'svelte';
    import { onDestroy } from 'svelte';
    import logoDark from '../assets/images/logo-blk-wt.png';
    import logoLight from '../assets/images/logo-wt-blk.png';
    import Modal from './Modal.svelte';
    import { supabase } from '../supabaseClient';

    let menu = false;
    let loading = false;
    let modalTypeToShow = null; // Declare modalTypeToShow at the top level
    let isAuthenticated = false; // Track authentication state

    // Check authentication status on mount
    onMount(async () => {
        handleRouteChange();

        // Subscribe to authentication state changes
        const { data: authListener } = supabase.auth.onAuthStateChange((event, session) => {
            // Update isAuthenticated based on session presence
            isAuthenticated = session !== null;
        });

        // Initial check for authentication status
        const session = supabase.auth.session();
        isAuthenticated = session !== null;

        return () => {
            // Unsubscribe from authentication state changes when component is destroyed
            authListener.unsubscribe();
        };
    });

    const handleRouteChange = () => {
        loading = false;
    };

    function handleAnchorClick(event) {
        event.preventDefault();
        const link = event.currentTarget;
        const anchorId = new URL(link.href).hash.replace('#', '');
        const anchor = document.getElementById(anchorId);
        window.scrollTo({
            top: anchor.offsetTop,
            behavior: 'smooth'
        });
    }

    // Define openModal function
    function openModal(modalType) {
        console.log('Opening modal:', modalType); // Log a message to console
        // Set the modalTypeToShow to trigger modal display
        modalTypeToShow = modalType;
    }

    // Function to handle sign out
    async function handleSignOut() {
        try {
            loading = true;
            const { error } = await supabase.auth.signOut();
            if (error) throw error;
            // Update authentication state after sign out
            isAuthenticated = false;
        } catch (error) {
            console.error('Sign out error:', error.message);
        } finally {
            loading = false;
        }
    }
</script>

<Modal {modalTypeToShow} />
<!-- Render the Modal component with modalType prop -->

<nav class="navbar" id="navbar">
    <div class="container relative flex flex-wrap items-center justify-between">
        <a class="navbar-brand md:me-8" href="/">
            <img src={logoDark} class="inline-block dark:hidden" alt="" />
            <img src={logoLight} class="hidden dark:inline-block" alt="" />
        </a>

        <div class="nav-icons flex items-center lg_992:order-2 ms-auto md:ms-8">
            {#if isAuthenticated}
                <!-- If authenticated, show Sign Out button -->
                <button
                    type="button"
                    class="h-8 px-4 text-[12px] tracking-wider inline-flex items-center justify-center font-medium rounded-md bg-teal-500 text-white uppercase"
                    on:click={handleSignOut}
                    disabled={loading}
                >
                    {loading ? 'Signing Out...' : 'Sign Out'}
                </button>
            {:else}
                <!-- If not authenticated, show Login button -->
                <button
                    type="button"
                    class="h-8 px-4 text-[12px] tracking-wider inline-flex items-center justify-center font-medium rounded-md bg-teal-500 text-white uppercase"
                    on:click={() => openModal('login')}
                >
                    Login
                </button>
            {/if}
            <button
                data-collapse="menu-collapse"
                type="button"
                class="collapse-btn inline-flex items-center ms-2 text-dark dark:text-white lg_992:hidden"
                on:click={() => (menu = !menu)}
            >
                <span class="sr-only">Navigation Menu</span>
                <i class="mdi mdi-menu text-[24px]" />
            </button>
        </div>

        <div
            class={`navigation lg_992:order-1 lg_992:flex  ms-auto ${menu ? '' : 'hidden'}`}
            id="menu-collapse"
        >
            <ul class="navbar-nav" id="navbar-navlist">
				<li class="nav-item ms-0">
					<a
						class="nav-link active home"
						href="#home"
						on:click={handleAnchorClick}
						smooth={true}
						duration={1000}
						activeClass="active"
						spy={true}>Home</a
					>
				</li>
				<li class="nav-item ms-0">
					<a
						class="nav-link about"
						href="#about"
						on:click={handleAnchorClick}
						smooth={true}
						duration={1000}
						activeClass="active"
						spy={true}>About</a
					>
				</li>
				<li class="nav-item ms-0">
					<a
						class="nav-link services"
						href="#services"
						on:click={handleAnchorClick}
						smooth={true}
						duration={1000}
						activeClass="active"
						spy={true}>Info</a
					>
				</li>
				<li class="nav-item ms-0">
					<a
						class="nav-link review"
						href="#review"
						on:click={handleAnchorClick}
						smooth={true}
						duration={1000}
						activeClass="active"
						spy={true}>Testimonial</a
					>
				</li>
				<li class="nav-item ms-0">
					<a
						class="nav-link pricing"
						href="#pricing"
						on:click={handleAnchorClick}
						smooth={true}
						duration={1000}
						activeClass="active"
						spy={true}>Subscribe</a
					>
				</li>
				<li class="nav-item ms-0">
					<a
						class="nav-link contact"
						href="#contact"
						on:click={handleAnchorClick}
						smooth={true}
						duration={1000}
						activeClass="active"
						spy={true}>Contact us</a
					>
				</li>
			</ul>
		</div>
	</div>
</nav>
