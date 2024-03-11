<script>
    import { Splide, SplideSlide } from "@splidejs/svelte-splide";
    import "@splidejs/svelte-splide/css";
    // or only core styles
    import "@splidejs/svelte-splide/css/core";
    import client1 from '../assets/images/team/01.jpg';
    import client2 from '../assets/images/team/02.jpg';
    import client3 from '../assets/images/team/03.jpg';
    import client4 from '../assets/images/team/04.jpg';
    import client5 from '../assets/images/team/05.jpg';
    import client6 from '../assets/images/team/06.jpg';

    const clientData = [
    {
        image:client1,
        name:'Calvin Carlo',
        title:'Manager',
        desc:'" It seems that only fragments of the original text remain in the Lorem Ipsum texts used today. "'
    },
    {
        image:client2,
        name:'Christa Smith',
        title:'Manager',
        desc:'" The most well-known dummy text is the Lorem Ipsum, which is said to have originated in the 16th century. "'
    },
    {
        image:client3,
        name:'Jemina CLone',
        title:'Manager',
        desc:'" One disadvantage of Lorum Ipsum is that in Latin certain letters appear more frequently than others"'
    },
    {
        image:client4,
        name:'Smith Vodka',
        title:'Manager',
        desc:'" Thus, Lorem Ipsum has only limited suitability as a visual filler for German texts "'
    },
    {
        image:client5,
        name:'Cristino Murfi',
        title:'Manager',
        desc:'" There is now an abundance of readable dummy texts. These are usually used when a text is required"'
    },
    {
        image:client6,
        name:'Cristino Murfi',
        title:'Manager',
        desc:'" According to most sources, Lorum Ipsum can be traced back to a text composed by Cicero "'
    },
];

const settings = {
    container: '.tiny-three-item',
    controls: false,
    mouseDrag: true,
    loop: true,
    rewind: true,
    autoplay: true,
    autoplayButtonOutput: false,
    autoplayTimeout: 3000,
    speed: 400,
    gutter: 12,
    perPage: 3,
    arrows:false,
    breakpoints: {
        992: {
            perPage: 3
        },

        767: {
            perPage: 2
        },

        320: {
            perPage: 1
        }
    },
};

</script>
<section class="relative md:py-24 py-16" id="review">
    <div class="container relative">
        <div class="grid grid-cols-1 pb-6 text-center">
            <h3 class="font-semibold text-2xl leading-normal mb-4">What Our Users Say</h3>

            <p class="text-slate-400 max-w-xl mx-auto">This is just a simple text made for this unique and awesome template, you can replace it with any text.</p>
        </div>

        <div class="grid grid-cols-1 mt-6">
            <div class="tiny-three-item">
                <Splide aria-label="My Favorite Images" options={settings}>
                    {#each clientData as item}
                        <SplideSlide>
                        <div class="tiny-slide text-center">
                            <div class="cursor-e-resize">
                                <div class="content relative rounded shadow dark:shadow-gray-700 m-2 p-6 bg-white dark:bg-slate-900 before:content-[''] before:absolute before:start-1/2 before:-bottom-[4px] before:box-border before:border-8 before:rotate-[45deg] before:border-t-transparent before:border-e-white dark:before:border-e-slate-900 before:border-b-white dark:before:border-b-slate-900 before:border-s-transparent before:shadow-testi dark:before:shadow-gray-700 before:origin-top-left">
                                    <i class="mdi mdi-format-quote-open mdi-48px text-teal-500"></i>
                                    <p class="text-slate-400">{item.desc}</p>
                                    <ul class="list-none mb-0 text-amber-400 mt-3">
                                        <li class="inline"><i class="mdi mdi-star"></i></li>
                                        <li class="inline"><i class="mdi mdi-star"></i></li>
                                        <li class="inline"><i class="mdi mdi-star"></i></li>
                                        <li class="inline"><i class="mdi mdi-star"></i></li>
                                        <li class="inline"><i class="mdi mdi-star"></i></li>
                                    </ul>
                                </div>
                                
                                <div class="text-center mt-5">
                                    <img src={item.image} class="size-14 rounded-full shadow-md dark:shadow-gray-700 mx-auto" alt=""/>
                                    <h6 class="mt-2 font-semibold">{item.name}</h6>
                                    <span class="text-slate-400 text-sm">{item.title}</span>
                                </div>
                            </div>
                        </div>
                        </SplideSlide>
                    {/each}
                </Splide>
            </div>
        </div>
    </div>
</section>