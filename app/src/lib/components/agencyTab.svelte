<script>
    import blog1 from '../assets/images/blog/01.jpg'
    import blog2 from '../assets/images/blog/02.jpg'
    import blog3 from '../assets/images/blog/03.jpg';
let activeIndex = 1;
</script>
<section class="realtive md:py-24 py-16">
    <div class="container relative">
        <div class="grid grid-cols-1 pb-6 text-center">
            <h3 class="font-semibold text-2xl leading-normal mb-4">A Performance-driven Marketing Agency</h3>

            <p class="text-slate-400 max-w-xl mx-auto">This is just a simple text made for this unique and awesome template, you can replace it with any text.</p>
        </div>

        <div class="grid md:grid-cols-12 grid-cols-1 mt-6 gap-6">
            <div class="lg:col-span-4 md:col-span-5">
                <div class="sticky top-20">
                    <ul class="flex-column p-6 bg-white dark:bg-slate-900 shadow dark:shadow-gray-700 rounded-md">
                        <li role="presentation">
                            <button class={`px-4 py-2 text-start text-base font-medium rounded-md w-full hover:text-teal-500 duration-500 ${activeIndex === 1 ? 'text-white bg-teal-500 hover:text-white' : ''}`} on:click={() => activeIndex = 1}>
                                <span class="block">Step 1</span>
                                <span class="text-lg mt-2 block">SEO Audit</span>
                                <span class="block mt-2">We offer flexible and comprehensive online marketing plans</span>
                            </button>
                        </li>
                        <li role="presentation">
                            <button class={`px-4 py-2 text-start text-base font-medium rounded-md w-full mt-6 hover:text-teal-500 duration-500 ${activeIndex === 2 ? 'text-white bg-teal-500 hover:text-white' : ''}`} on:click={() => activeIndex = 2}>
                                <span class="block">Step 2</span>
                                <span class="text-lg mt-2 block">Project Execution</span>
                                <span class="block mt-2">We offer flexible and comprehensive online marketing plans</span>
                            </button>
                        </li>
                        <li role="presentation">
                            <button class={`px-4 py-2 text-start text-base font-medium rounded-md w-full mt-6 hover:text-teal-500 duration-500 ${activeIndex === 3 ? 'text-white bg-teal-500 hover:text-white' : ''}`} on:click={() => activeIndex = 3}>
                                <span class="block">Step 3</span>
                                <span class="text-lg mt-2 block">Results & Reporting</span>
                                <span class="block mt-2">We offer flexible and comprehensive online marketing plans</span>
                            </button>
                        </li>
                    </ul>
                </div>
            </div>

            <div class="lg:col-span-8 md:col-span-7">
                <div id="myTabContent" class="p-6 bg-white dark:bg-slate-900 shadow dark:shadow-gray-700 rounded-md">
                    <div class={activeIndex === 1 ? '' : 'hidden' }>
                        <img src={blog1} class="shadow dark:shadow-gray-700 rounded-md" alt=""/>

                        <div class="mt-6">
                            <h5 class="text-lg font-medium">SEO Audit</h5>
                            <p class="text-slate-400 mt-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Itaque, impedit vitae. Nobis, similique omnis cumque sapiente laboriosam animi quod cupiditate?</p>
                            <div class="mt-4">
                                <a href="/" class="text-teal-500">Read More <i class="mdi mdi-chevron-right align-middle"></i></a>
                            </div>
                        </div>
                    </div>
                    <div class={activeIndex === 2 ? '' : 'hidden' }>
                        <img src={blog2} class="shadow dark:shadow-gray-700 rounded-md" alt=""/>

                        <div class="mt-6">
                            <h5 class="text-lg font-medium">Project Execution</h5>
                            <p class="text-slate-400 mt-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Itaque, impedit vitae. Nobis, similique omnis cumque sapiente laboriosam animi quod cupiditate?</p>
                            <div class="mt-4">
                                <a href="/" class="text-teal-500">Read More <i class="mdi mdi-chevron-right align-middle"></i></a>
                            </div>
                        </div>
                    </div>
                    <div class={activeIndex === 3 ? '' : 'hidden' }>
                        <img src={blog3} class="shadow dark:shadow-gray-700 rounded-md" alt=""/>

                        <div class="mt-6">
                            <h5 class="text-lg font-medium">Results & Reporting</h5>
                            <p class="text-slate-400 mt-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Itaque, impedit vitae. Nobis, similique omnis cumque sapiente laboriosam animi quod cupiditate?</p>
                            <div class="mt-4">
                                <a href="/" class="text-teal-500">Read More <i class="mdi mdi-chevron-right align-middle"></i></a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>