<script>
    import { TrendingUpIcon,PauseIcon,CompassIcon,CommandIcon,HexagonIcon,MaximizeIcon,BellIcon,MonitorIcon } from 'svelte-feather-icons';
    const servicesData = [  
        {
            icon:TrendingUpIcon,
            title:'Empowering Women',
            desc:'Ensuring equal pay for women empowers them by recognizing their invaluable contributions and talents on par with men, fostering a more equitable society where individuals are valued based on merit rather than gender.'
        },
        {
            icon:PauseIcon,
            title:'Gender Equality in Sports',
            desc:'Gender equality in sports is achieved when athletes of all genders have equal opportunities for participation, access to resources, recognition, and support, creating a level playing field where talent and dedication determine success rather than gender.'
        },
        {
            icon:CompassIcon,
            title:'Limited Edition Clothing Drops',
            desc:'Limited edition clothing drops offer a unique opportunity for fashion enthusiasts to own exclusive pieces that reflect their individuality and style, fostering a sense of exclusivity and excitement within the fashion community.'
        },
        {
            icon:CommandIcon,
            title:'Collaborations',
            desc: 'In our collaborative efforts, we partner with like-minded organizations and individuals to drive positive change and innovation in disc golf. Through shared visions and combined expertise, we aim to create impactful projects, events, and initiatives that benefit the entire disc golf community.'
        },
        {
            icon:HexagonIcon,
            title:'Competition',
            desc:'Simply put, FLI Golf tournaments will be unmatched with anything happening in the sport of disc golf today.'
        },
        {
            icon:MaximizeIcon,
            title:'About',
            desc:'The management team of FLI Golf has years of experience in the sports, entertainment, and business management industries, which has allowed FLI Golf to secure a major production partner, ensuring live play media coverage'
        },
        {
            icon: BellIcon,
            title: 'Social Media',
            desc: "In disc golf social media, we amplify community voices, foster connections, and promote the sport's spirit. Join us in shaping an inclusive space for enthusiasts to share, celebrate, and evolve disc golf culture."
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
            <h3 class="font-semibold text-2xl leading-normal mb-4">Info</h3>

            <p class="text-slate-400 max-w-xl mx-auto">Equality isn't just a goal – it's a fundamental value we uphold in everything we do. We're committed to breaking down gender barriers and promoting equality in disc golf and beyond.</p>
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