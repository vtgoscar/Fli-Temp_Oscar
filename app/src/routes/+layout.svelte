<script lang="ts">
	import { onMount, tick } from 'svelte';
	import '../app.css';
	import '../assets/css/tailwind.css';
	import '../assets/css/materialdesignicons.min.css';
	import { supabase } from '/src/supabaseClient.ts';
	import type { AuthSession } from '@supabase/supabase-js';
	import Account from '/workspace/Fli-Temp/app/src/lib/Account.svelte';
	import { goto } from '$app/navigation';
  import { page } from '$app/stores';


	onMount(async () => {
		window.addEventListener('scroll', windowScroll);
	});
	/**
	 * Window scroll
	 */
	function windowScroll() {
		const navbar = document.getElementById('navbar');
		if (document.body.scrollTop >= 50 || document.documentElement.scrollTop >= 50) {
			// @ts-ignore
			navbar.classList.add('is-sticky');
		} else {
			// @ts-ignore
			navbar.classList.remove('is-sticky');
		}
	}

	let url: { pathname: string };
	let showNavBar = false;
	let isHomePage = false;

	let session: any = null;
	let role:
		| 'Admin'
		| 'Participant'
		| 'Pro'
		| 'Subscriber'
		| 'Venue'
		| 'Team'
		| 'Scorer'
		| 'Past Subscriber'
		| null = null;
	let showUpdatePasswordForm = false;
	let newPassword = '';
	let userRole = null;
	let hasSigned = null;

	async function fetchUserRoleAndSignStatus(userId: any) {
		const { data, error } = await supabase
			.from('profiles')
			.select('role, has_signed, subscriber')
			.eq('id', userId)
			.single();

		if (error) {
			console.error('Error fetching user role:', error);
			return;
		}

		userRole = data.role;
		hasSigned = data.has_signed;
		console.log('User role is:', userRole);
		console.log(123);

		// Redirect based on user role I do not think it runs this code it does that below
		switch (userRole) {
			case 'Scorer':
				goto('/scoring'); // Redirect Scorer to the scoring page
				break;
			case 'Subscriber':
				goto('/fantasy'); // Redirect Subscriber to the fantasy page
				break;
			case 'Pro':
				if (!hasSigned) {
					goto('/intent'); // Redirect to the 'intent' route for Pros who haven't signed
				}
				break;
			default:
				goto('/'); // Redirect to the home page for other roles or conditions
				break;
		}
	}

	async function fetchUserRole(userId: string) {
		const { data, error } = await supabase
			.from('profiles')
			.select('role')
			.eq('id', userId) // id is the column that relates to the auth user's id
			.single();

		if (error) {
			console.error('Error fetching user role:', error);
			return null;
		}

		if (!data) {
			console.warn(`No profile found for user with id: ${userId}`);
			return null;
		}

		return data.role;
	}

	function toggleNavBar() {
		showNavBar = !showNavBar;
	}

	// Add an async function to fetch the user's profile
	async function fetchUserProfile(userId: string) {
		const { data, error } = await supabase.from('profiles').select('*').eq('id', userId).single();

		if (error) {
			console.error('Error fetching user profile:', error);
			return null;
		}

		return data;
	}

	// Subscribe to auth state changes
	supabase.auth.onAuthStateChange(async (event, newSession) => {
		session = newSession;
		console.log('Session updated:', session);

		if (session) {
			// Fetch the user's profile when the session is updated
			const userProfile = await fetchUserProfile(session.user.id);
			// Use the user's profile data as needed
		}
	});

	function handleRoleBasedRedirect(role, hasSigned) {
		const currentRoute = window.location.pathname;

		// Add logic here to determine if a redirect is needed based on role and current route
		if (role === 'Scorer' && currentRoute !== '/scoring') {
			goto('/scoring');
		} else if (role === 'Pro' && !hasSigned && currentRoute !== '/intent') {
			goto('/intent');
		} // Add other conditions as needed
	}

	let isBrowser = typeof window !== 'undefined'; // Check if in a browser environment

	let isSmallScreen = typeof window !== 'undefined' && window.innerWidth <= 768;

	$: console.log('Current session:', session);
	$: ({ url } = $page);
	$: isHomePage = url.pathname === '/';
	$: console.log(url.pathname);
	$: console.log('URL value:', url);
	console.log('NavBar rendered');
	$: {
		console.log('Reactive statement ran', isSmallScreen, isHomePage);
	}

	// Check the screen size on component mount and whenever the window is resized
	onMount(() => {
		function checkScreenSize() {
			isSmallScreen = window.innerWidth <= 768;
		}

		window.addEventListener('resize', checkScreenSize);

		return () => {
			window.removeEventListener('resize', checkScreenSize);
		};
		initializeStores();
	});

	let isLoggedIn = false;
	let formType;


	async function setFormToRegister() {
		await tick(); // Wait for the DOM to update
	}

	const signOut = async () => {
		try {
			await supabase.auth.signOut();
			session = null;
			userRole = null;
			// Navigate user to a desired location after sign out, if necessary:
			// window.location.href = '/login';
		} catch (error) {
			console.error('Error signing out: ', error);
		}
	};


	async function handlePasswordResetRequest() {
		if (session && session.user?.email) {
			const { data, error } = await supabase.auth.resetPasswordForEmail(session.user?.email, {
				redirectTo: 'https://fligolf.netlify.app/api/auth/callback?next=/account/update-password'
			});

			if (error) {
				console.error('Error sending password reset:', error.message);
			} else {
				console.log('Password reset email sent:', data);
			}
		}
	}

	async function handleUpdatePasswordEvent(event: {
		detail: { currentPassword: any; newPassword: any };
	}) {
		const { currentPassword, newPassword } = event.detail;

		// Check if you want to use the current password in some way for validation
		// Otherwise, continue with the existing logic

		if (newPassword && session) {
			const { data, error } = await supabase.auth.updateUser({ password: newPassword });

			if (error) {
				console.error('Error updating password:', error.message);
			} else {
				console.log('Password updated successfully:', data);
				showUpdatePasswordForm = false;
			}
		}
	}


	function toggleRegister() {
		const currentRoute = window.location.pathname;

		if (currentRoute !== '/' && currentRoute !== '/index.html') {
			// Redirect to the root with a special query parameter
			window.location.href = '/?showRegister=true';
		} else {
			// If already on the root, just show the registration form
			setFormToRegister();
		}
	}

	function toggleSubscribePopUp() {
		toggleOverlayForm('subscribe');
	}

	function showPasswordUpdateForm() {
		showUpdatePasswordForm = true;
	}

	let showRegister: boolean = false;

	$: {
		const query = new URLSearchParams($page.query);
		showRegister = query.get('showRegister') === 'true';

		if (showRegister) {
			setFormToRegister();

			// Optional: Clean up the URL after showing the form
			const cleanURL = window.location.pathname;
			window.history.replaceState(null, '', cleanURL);
		}
	}
	$: {
		const query = new URLSearchParams($page.query);
		const showRegister = query.get('showRegister') === 'true';

		if (showRegister) {
			setFormToRegister();
			window.history.replaceState(null, '', window.location.pathname); // Clean up the URL
		}
	}
</script>

<Account />
<slot />
