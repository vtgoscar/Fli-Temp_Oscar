<script>
    import { TrendingUpIcon,DollarSignIcon,CompassIcon,CommandIcon,InboxIcon,CameraIcon,BellIcon,MonitorIcon } from 'svelte-feather-icons';
    const servicesData = [  
        {
            icon:TrendingUpIcon,
            title:'Grow Your Business',
            desc:'If the distribution of letters and words is random, the reader will not be distracted from making.'
        },
        {
            icon:DollarSignIcon,
            title:'Drive More Sales',
            desc:'If the distribution of letters and words is random, the reader will not be distracted from making.'
        },
        {
            icon:CompassIcon,
            title:'Handled By Expert',
            desc:'If the distribution of letters and words is random, the reader will not be distracted from making.'
        },
        {
            icon:CommandIcon,
            title:'Discussion For Idea',
            desc:'If the distribution of letters and words is random, the reader will not be distracted from making.'
        },
        {
            icon:InboxIcon,
            title:'Web Design',
            desc:'If the distribution of letters and words is random, the reader will not be distracted from making.'
        },
        {
            icon:CameraIcon,
            title:'Network Security',
            desc:'If the distribution of letters and words is random, the reader will not be distracted from making.'
        },
        {
            icon:BellIcon,
            title:'Social Media',
            desc:'If the distribution of letters and words is random, the reader will not be distracted from making.'
        },
        {
            icon:MonitorIcon,
            title:'Design & Branding',
            desc:'If the distribution of letters and words is random, the reader will not be distracted from making.'
        },
    ];
</script>

<section class="relative md:py-24 py-16 bg-slate-50 dark:bg-slate-800" id="services">
    <div class="container relative">
        <div class="grid grid-cols-1 pb-6 text-center">
            <h3 class="font-semibold text-2xl leading-normal mb-4">Our Services</h3>

            <p class="text-slate-400 max-w-xl mx-auto">This is just a simple text made for this unique and awesome template, you can replace it with any text.</p>
        </div>

        <div class="grid lg:grid-cols-4 md:grid-cols-2 sm:grid-cols-2 grid-cols-1 gap-6 mt-6">
           {#each servicesData as item}
           {@const Icon=item.icon}
                    <div class="group rounded-md shadow dark:shadow-gray-700 relative bg-white dark:bg-slate-900 p-6 overflow-hidden h-fit">
                        <div class="flex items-center justify-center size-14 -rotate-45 bg-gradient-to-r from-transparent to-teal-500/10 text-teal-500 text-center rounded-full group-hover:bg-teal-500/10 duration-500">
                             <Icon class="size-6 rotate-45"></Icon>
                        </div>

                        <div class="content mt-6 relative z-1">
                            <a href="/" class="title text-lg font-semibold hover:text-teal-500">{item.title}</a>
                            <p class="text-slate-400 mt-3">{item.desc}</p>

                            <div class="mt-6">
                                <a href="/" class="text-teal-500">Read More <i class="mdi mdi-chevron-right align-middle"></i></a>
                            </div>
                        </div>

                        <div class="absolute bottom-0 -end-16">
                             <Icon class="size-48 text-teal-500 opacity-[0.04] dark:opacity-[0.04] group-hover:opacity-10 duration-500"></Icon>
                        </div>
                    </div>
                
                    {/each}
        </div>
    </div>
</section>