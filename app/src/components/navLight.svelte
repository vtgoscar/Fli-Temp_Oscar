<script>
    import { onMount } from "svelte";
    import logoDark from '../assets/images/logo-dark.png';
    import logoLight from '../assets/images/logo-light.png';
    let menu = false;
    let loading = false;
    let scroll = false;
onMount(() => {
    handleRouteChange();
    window.addEventListener("scroll", () => {
        scroll = window.scrollY > 50;
    });
    window.onscroll = () => {
    
      const sections = document.querySelectorAll("section");
      const navLi = document.querySelectorAll(".navbar ul.navbar-nav > li");
      var current = "";

    sections.forEach((section) => {
      const sectionTop = section.offsetTop;
      if (pageYOffset >= sectionTop - 60) {
        current = section.getAttribute("id"); }
    });
    

    navLi.forEach((li) => {
      li.classList.remove("active");
      console.log()
      if (li.classList.contains(current)) {
        console.log('in')
        li.classList.add("active");
      }
    });
  };
  });

  const handleRouteChange = () => {
    loading = false;
  };

function handleAnchorClick (event) {
		event.preventDefault()
		const link = event.currentTarget
		const anchorId = new URL(link.href).hash.replace('#', '')
		const anchor = document.getElementById(anchorId)
		window.scrollTo({
			top: anchor.offsetTop,
			behavior: 'smooth'
		})
	}
</script>
<nav class={`navbar ${scroll ? 'is-sticky' : ''}`} id="navbar">
    <div class="container relative flex flex-wrap items-center justify-between">
        <a class="navbar-brand md:me-8" href="/">
            <span class="inline-block dark:hidden">
                <img src={logoDark} class="l-dark" alt=""/>
                <img src={logoLight} class="l-light" alt=""/>
            </span>
            <img src={logoLight} class="hidden dark:inline-block" alt=""/>
        </a>

        <div class="nav-icons flex items-center lg_992:order-2 ms-auto md:ms-8">
            <ul class="list-none menu-social mb-0">
                <li class="inline">
                    <a href="/" class="h-8 px-4 text-[12px] tracking-wider inline-flex items-center justify-center font-medium rounded-md bg-teal-500 text-white uppercase">Login</a>
                </li>
            </ul>
            <button data-collapse="menu-collapse" type="button" class="collapse-btn inline-flex items-center ms-2 text-dark dark:text-white lg_992:hidden" on:click={() => menu = !menu}>
                <span class="sr-only">Navigation Menu</span>
                <i class="mdi mdi-menu text-[24px]"></i>
            </button>
        </div>

        <div class={`navigation lg_992:order-1 lg_992:flex  ms-auto ${menu ? '' : 'hidden'}`} id="menu-collapse">
            <ul class="navbar-nav nav-light sidebar-nav" id="navbar-navlist">
                <li class="nav-item active home">
                    <a class="nav-link ms-0" href="#home" on:click={handleAnchorClick} smooth={true} duration={1000} activeClass='active' spy={true}>Home</a>
                </li>
                <li class="nav-item about">
                    <a class="nav-link ms-0" href="#about" on:click={handleAnchorClick} smooth={true} duration={1000} activeClass='active' spy={true}>About</a>
                </li>
                <li class="nav-item services">
                    <a class="nav-link ms-0" href="#services" on:click={handleAnchorClick} smooth={true} duration={1000} activeClass='active' spy={true}>Services</a>
                </li>
                <li class="nav-item review">
                    <a class="nav-link ms-0" href="#review" on:click={handleAnchorClick} smooth={true} duration={1000} activeClass='active' spy={true}>Testimonial</a>
                </li>
                <li class="nav-item pricing">
                    <a class="nav-link ms-0" href="#pricing" on:click={handleAnchorClick} smooth={true} duration={1000} activeClass='active' spy={true}>Pricing</a>
                </li>
                <li class="nav-item blog">
                    <a class="nav-link ms-0" href="#blog" on:click={handleAnchorClick} smooth={true} duration={1000} activeClass='active' spy={true}>Blogs</a>
                </li>
                <li class="nav-item contact">
                    <a class="nav-link ms-0" href="#contact" on:click={handleAnchorClick} smooth={true} duration={1000} activeClass='active' spy={true}>Contact us</a>
                </li>
            </ul>
        </div>
    </div>
</nav>