<script>	
	import Header from "../../../components/navLight.svelte";
	import About from "../../../components/about.svelte";
	import Services from '../../../components/services.svelte';
	import AgencyTab from "../../../components/agencyTab.svelte";
	import Cta from "../../../components/cta.svelte";
	import Client from "../../../components/client.svelte";
	import Pricing from "../../../components/pricing.svelte";
	import Blogs from "../../../components/blog.svelte";
	import GetInTouch from "../../../components/getInTuoch.svelte";
	import Footer from "../../../components/footer.svelte";
	import Switcher from "../../../components/switcher.svelte";
</script>
<Header />
<slot />
<About/>
<Services/>
<AgencyTab/>
<Cta/>
<Client/>
<Pricing/>
<Blogs/>
<GetInTouch/>
<Footer/>
<Switcher/>