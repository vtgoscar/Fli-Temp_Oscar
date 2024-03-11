<script>
    import aboutImage from '../assets/images/group-fli-1.jpg';
    import Counter from './counter.svelte';
</script>
<Counter />
<section class="relative md:py-24 py-16" id="about">
    <div class="container relative">
        <div class="grid md:grid-cols-12 grid-cols-1 items-center gap-6">
            <div class="md:col-span-6">
                <div class="lg:me-8">
                    <div class="relative">
                        <img src={aboutImage} class="rounded-full shadow dark:shadow-gray-700" alt=""/>
                    </div>
                </div>
            </div>

            <div class="md:col-span-6">
                <div class="lg:ms-8">
                    <h6 class="text-teal-500 text-sm font-semibold uppercase mb-2">Who Are We ?</h6>
                    <h3 class="font-semibold text-2xl leading-normal mb-4">We're a global stakeholder <br/> relations and partnership <br/> building consultancy.</h3>

                    <p class="text-slate-400 max-w-xl mb-6">Get instant helpful resources about anything on the go, easily implement secure money transfer solutions, boost your daily efficiency, connect to other app users and create your own Techwind network, and much more with just a few taps. commodo consequat. Duis aute irure.</p>

                    <a href="/" class="h-10 px-6 tracking-wide inline-flex items-center justify-center font-medium rounded-md bg-teal-500 text-white">Read More <i class="mdi mdi-chevron-right align-middle ms-0.5"></i></a>
                </div>
            </div>
        </div>
    </div>
</section>