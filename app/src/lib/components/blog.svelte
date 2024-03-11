<script>
    import blog1 from '../assets/images/blog/01.jpg';
    import blog2 from '../assets/images/blog/02.jpg';
    import blog3 from '../assets/images/blog/03.jpg';
    import {CalendarIcon,ClockIcon } from 'svelte-feather-icons';
    
    const blogData = [
    {
        image:blog1,
        title:'Design your apps in your own way',
        desc:'This is required when, for example, the final text is not yet available.',
        date:'13th March 2023'
    },
    {
        image:blog2,
        title:'How apps is changing the IT world',
        desc:'This is required when, for example, the final text is not yet available.',
        date:'5th May 2023'
    },
    {
        image:blog3,
        title:'Smartest Applications for Business',
        desc:'This is required when, for example, the final text is not yet available.',
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