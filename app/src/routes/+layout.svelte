<script>
	import { onMount } from "svelte";
	import "../app.css";
	import "../assets/css/tailwind.css";
	import '../assets/css/materialdesignicons.min.css';

	onMount(async () => {
    window.addEventListener("scroll", windowScroll);
  });
  /**
   * Window scroll
   */
  function windowScroll() {
    const navbar = document.getElementById("navbar");
    if (
      document.body.scrollTop >= 50 ||
      document.documentElement.scrollTop >= 50
    ) {
      // @ts-ignore
      navbar.classList.add("is-sticky");
    } else {
      // @ts-ignore
      navbar.classList.remove("is-sticky");
    }
  }
  
</script>
<slot />