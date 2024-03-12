<script>
    import groupImage from '../assets/images/group-fli-1.jpg';
    import Counter from './counter.svelte';
</script>
<Counter />
<section class="relative md:py-24 py-16" id="about">
    <div class="container relative">
        <div class="grid md:grid-cols-12 grid-cols-1 items-center gap-6">
<div class="md:col-span-6">
    <div class="lg:me-8">
        <figure class="relative">
            <img src={groupImage} class="rounded-full shadow dark:shadow-gray-700" alt=""/>
            <figcaption style="text-align: center;">Andrew Panza, Dustin Dinsmore, Tony Smart, Mark Colemann and Corey LaRusso</figcaption>
        </figure>
    </div>
</div>

            <div class="md:col-span-6">
                <div class="lg:ms-8">
                    <h6 class="text-teal-500 text-sm font-semibold uppercase mb-2">Welcome to FLI Golf:</h6>
                    <h3 class="font-semibold text-2xl leading-normal mb-4">Our Mission: <br/> Redefine Disc Golf with Purpose <br/> building consultancy.</h3>

                    <p class="text-slate-500 max-w-xl mb-6">It is simple yet profound: to redefine the disc golf experience while fostering a culture of inclusivity, empowerment, and equality. Disc golf isn't just a game to us – it's a platform for progress, a catalyst for change, and a community united by passion.</p>

                    <a href="/" class="h-10 px-6 tracking-wide inline-flex items-center justify-center font-medium rounded-md bg-teal-500 text-white">Read More <i class="mdi mdi-chevron-right align-middle ms-0.5"></i></a>
                </div>
            </div>
        </div>
    </div>
</section>