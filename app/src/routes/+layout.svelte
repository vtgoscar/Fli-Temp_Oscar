<script>
  import { onMount } from 'svelte';
  import '../app.postcss';
  import '/workspace/Fli-Temp/app/assets/css/tailwind.css';
  import '/workspace/Fli-Temp/app/assets/css/materialdesignicons.min.css';

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
</script>

<div>
  <div class="ml-36">
    <div class="flex items-center justify-between">
      <div class="flex items-center">
        <!-- Container for the logo and text -->
        <a href="/" class="mr-8">
          <!-- Use mr-8 to add space between the logo and menu items -->
          <img src="/FLI_BLK.png" alt="FLI GOLF Logo" class="logo-class w-1/2" />
          <!-- Logo -->
        </a>
        <div class="text-white font-bold flex items-center whitespace-nowrap text-3xl">
          Shop <span class="mx-2">|</span>
        </div>
      </div>
      <!-- Apply ml-auto class to move the container with the logo and menu items to the right -->
      <div class="ml-auto">
        <!-- Adjusted margin-left value -->
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="52"
          height="52"
          viewBox="0 0 24 24"
          fill="currentColor"
        >
          <path d="M3 6h18v2H3zm0 5h18v2H3zm0 5h18v2H3z" />
        </svg>
      </div>
    </div>
  </div>
  <!-- Place the NavBar outside the AppBar -->
  <div class="flex justify-center">
  </div>
  <slot />
</div>

<style>
  .cursor-pointer {
    cursor: pointer;
  }

  .padded-button {
    padding: 8px;
  }
  .overlay {
    z-index: 1000; /* or any sufficiently high value */
    position: relative; /* or absolute, depending on your needs */
  }
  @media (max-width: 768px) {
    /* Adjust the layout for small screens */
    .flex {
      flex-direction: column;
    }
    .flex > div {
      margin-bottom: 10px; /* Add spacing between buttons */
    }
  }
  .fixed-nav-bar {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000; /* Adjust z-index as needed */
  }
</style>
