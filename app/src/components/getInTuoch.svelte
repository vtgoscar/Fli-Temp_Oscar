<script>
    import contact from '../assets/images/contact.svg';
    import { supabase } from '../supabaseClient';

    let first_name = '';
    let last_name = '';
    let email = '';
    let comments = '';
    let loading = false;
    let selectOption = '';

    const handleSubmit = async (event) => {
        event.preventDefault();
        try {
            loading = true;
            const { data, error } = await supabase.from('inquiries').insert([
                {
                    first_name: first_name,
                    last_name: last_name,
                    email: email,
                    comments: comments,
                    inquiry_type: selectOption
                }
            ]);
            if (error) throw error;
            console.log('Message sent successfully:', data);
            // Clear the form after successful submission
            first_name = '';
            last_name = '';
            email = '';
            comments = '';
            alert('Message sent successfully!');
        } catch (error) {
            console.error('Error sending message:', error);
            alert('Failed to send message. Please try again later.');
        } finally {
            loading = false;
        }
    };

    const validateEmail = (email) => {
        const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        return re.test(email);
    };
</script>

<section class="relative lg:py-24 py-16 bg-slate-50 dark:bg-slate-800" id="contact">
    <div class="container relative">
        <div class="grid grid-cols-1 pb-6 text-center">
            <h3 class="font-semibold text-2xl leading-normal mb-4">Get in touch!</h3>
            <p class="text-slate-400 max-w-xl mx-auto">
                Our team is dedicated to shaping the future of disc golf with innovation and exciting
                entertainment.
            </p>
        </div>

        <div class="grid md:grid-cols-12 grid-cols-1 items-center gap-6">
            <div class="lg:col-span-7 md:col-span-6">
                <img src={contact} alt="" />
            </div>

            <div class="lg:col-span-5 md:col-span-6">
                <div class="lg:ms-5">
                    <div class="bg-white dark:bg-slate-900 rounded-md shadow dark:shadow-gray-700 p-6">
                        <form on:submit={handleSubmit}>
                            <div class="grid lg:grid-cols-12 grid-cols-1 gap-3">
                                <div class="lg:col-span-6">
                                    <label for="first_name" class="font-semibold">First Name:</label>
                                    <input
                                        bind:value={first_name}
                                        id="first_name"
                                        type="text"
                                        class="mt-2 w-full py-2 px-3 h-10 bg-transparent dark:bg-slate-900 dark:text-slate-200 rounded outline-none border border-gray-100 dark:border-gray-800 focus:ring-0"
                                        placeholder="First Name"
                                    />
                                </div>

                                <div class="lg:col-span-6">
                                    <label for="last_name" class="font-semibold">Last Name:</label>
                                    <input
                                        bind:value={last_name}
                                        id="last_name"
                                        type="text"
                                        class="mt-2 w-full py-2 px-3 h-10 bg-transparent dark:bg-slate-900 dark:text-slate-200 rounded outline-none border border-gray-100 dark:border-gray-800 focus:ring-0"
                                        placeholder="Last Name"
                                    />
                                </div>

                                <div class="lg:col-span-12">
                                    <label for="email" class="font-semibold">Your Email:</label>
                                    <input
                                        bind:value={email}
                                        id="email"
                                        type="email"
                                        class="mt-2 w-full py-2 px-3 h-10 bg-transparent dark:bg-slate-900 dark:text-slate-200 rounded outline-none border border-gray-100 dark:border-gray-800 focus:ring-0"
                                        placeholder="Email"
                                        on:input={() => validateEmail(email)}
                                    />
                                    {#if !validateEmail(email)}
                                        <p class="text-red-500">Please enter a valid email.</p>
                                    {/if}
                                </div>

                                <div class="lg:col-span-12">
                                    <label for="selectOption" class="font-semibold">Select Option:</label>
                                    <select
                                        bind:value={selectOption}
                                        id="selectOption"
                                        class="mt-2 w-full py-2 px-3 h-10 bg-transparent dark:bg-slate-900"
                                        required
                                    >
                                        <option value="">Select an Option</option>
                                        <option value="collaborate">Collaborate with Us</option>
                                        <option value="partner">Partner with Us</option>
                                        <option value="marketing">Marketing Opportunities</option>
                                        <option value="sponsorship">Get Sponsored by Us</option>
                                        <option value="general">General Inquiry</option>
                                    </select>
                                    {#if selectOption === ''}
                                        <p class="text-red-500">Please select an option.</p>
                                    {/if}
                                </div>

                                <div class="lg:col-span-12">
                                    <label for="comments" class="font-semibold">Your Comment:</label>
                                    <textarea
                                        bind:value={comments}
                                        id="comments"
                                        class="mt-2 w-full py-2 px-3 h-28 bg-transparent dark:bg-slate-900 dark:text-slate-200 rounded outline-none border border-gray-100 dark:border-gray-800 focus:ring-0"
                                        placeholder="Message"
                                    />
                                </div>
                            </div>
                            <button
                                type="submit"
                                class="h-10 px-6 tracking-wide inline-flex items-center justify-center font-medium rounded-md bg-teal-500 text-white mt-2"
                                disabled={loading || !validateEmail(email) || selectOption === ''}
                            >
                                {loading ? 'Sending...' : 'Send Message'}
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>