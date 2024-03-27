<script>
    import blog1 from '../assets/images/blog/stock-exchange.webp';
    import blog2 from '../assets/images/blog/chocolates.webp';
    import blog3 from '../assets/images/blog/luxury-hotel-resort.webp';
    import {CalendarIcon,ClockIcon } from 'svelte-feather-icons';
    
    const blogData = [
    {
        image:blog1,
        title:'Economic Boost',
        desc:'Major sports tournaments attract a significant number of attendees, including players, celebrities, spectators, and media personnel. ',
        date:'13th March 2024'
    },
    {
        image:blog2,
        title:'Brand Exposure',
        desc:'Media coverage and promotional activities related to the event can increase the visibility of the venue, attracting more visitors in the long run.',
        date:'5th September 2023'
    },
    {
        image:blog3,
        title:'Tourism and Destination Attraction',
        desc:'A major sports tournament can turn the casino and resort into a destination for sports enthusiasts.',
        date:'19th June 2023'
    },
];
</script>
<section class="relative md:py-24 py-16" id="blog">
    <div class="container relative">
        <div class="grid grid-cols-1 pb-6 text-center">
            <h3 class="font-semibold text-2xl leading-normal mb-4">Blog or News</h3>

            <p class="text-slate-400 max-w-xl mx-auto">This is just a simple text made for this unique and awesome template, you can replace it with any text.</p>
        </div>

        <div class="grid lg:grid-cols-3 md:grid-cols-2 grid-cols-1 mt-6 gap-6">
            {#each blogData as item}
                <div class="group relative overflow-hidden">
                    <div class="relative overflow-hidden rounded-md shadow dark:shadow-gray-800">
                        <img src={item.image} class="group-hover:scale-110 duration-500" alt=""/>
                    </div>

                    <div class="mt-6">
                        <div class="flex mb-4">
                            <span class="flex items-center text-slate-400 text-sm"><CalendarIcon class="size-4 text-slate-900 dark:text-white me-1.5"/>{item.date}</span>
                            <span class="flex items-center text-slate-400 text-sm ms-3"><ClockIcon class="size-4 text-slate-900 dark:text-white me-1.5"/>5 min read</span>
                        </div>

                            <a href="/" class="title text-lg font-semibold hover:text-teal-500 duration-500 ease-in-out">{item.title}</a>
                        <p class="text-slate-400 mt-2">{item.desc}</p>

                        <div class="mt-3">
                            <a href="/" class="text-teal-500">Read More <i class="mdi mdi-chevron-right align-middle"></i></a>
                        </div>
                    </div>
                </div>
            {/each}
        </div>
    </div>
</section>