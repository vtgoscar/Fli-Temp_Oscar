<script>
   import bg from '../../../assets/images/bg/bg2.png'
</script>
<section class="relative flex items-center w-full py-36 lg:h-screen bg-gray-900 dark:bg-slate-800 bg-center bg-no-repeat bg-cover" style:background-image="url({bg})" id="home">
	<div class="container relative">
		<div class="grid lg:grid-cols-12 md:grid-cols-2 mt-10 items-center gap-[30px]">
			<div class="lg:col-span-7">
				<span class="bg-teal-500 text-white text-[12px] font-medium px-2.5 py-0.5 rounded h-5 mb-4">Business</span>
				<h4 class="font-semibold lg:leading-normal leading-normal tracking-wide text-4xl lg:text-5xl capitalize text-white mb-5">Welcome To Upcover</h4>
		
				<p class="text-white/70 text-lg max-w-xl">This is just a simple text made for this unique and awesome template, you can replace it with any text.</p>
			
				<div class="relative mt-6">
					<a href="/" class="h-10 px-6 tracking-wide inline-flex items-center justify-center font-medium rounded-md bg-teal-500 text-white">Get Started</a>
				</div>
			</div>

			<div class="lg:col-span-5">
				<div class="bg-white dark:bg-slate-900 rounded-xl shadow dark:shadow-gray-800 md:p-8 p-6 lg:ms-10 z-10 relative">
					<h4 class="mb-5 text-2xl font-semibold">We are offering 14 <br/> days free trial</h4>

					<form>
						<div class="grid grid-cols-1 gap-4">
							<div class="">
								<label for="name" class="form-label font-medium">Your Name :</label>
								<input type="text" class="mt-2 w-full py-2 px-3 h-10 bg-transparent dark:bg-slate-900 dark:text-slate-200 rounded outline-none border border-gray-100 dark:border-gray-800 focus:ring-0" placeholder="Name" name="name" required/>
							</div>

							<div class="">
								<label for="email" class="form-label font-medium">Your Email :</label>
								<input type="email" class="mt-2 w-full py-2 px-3 h-10 bg-transparent dark:bg-slate-900 dark:text-slate-200 rounded outline-none border border-gray-100 dark:border-gray-800 focus:ring-0" placeholder="Email" name="email" required/>
							</div>

							<div class="">
								<label for="phoneno" class="form-label font-medium">Phone No. :</label>
								<input name="number" id="phNumber" class="mt-2 w-full py-2 px-3 h-10 bg-transparent dark:bg-slate-900 dark:text-slate-200 rounded outline-none border border-gray-100 dark:border-gray-800 focus:ring-0" placeholder="+12 12458 854" required/>
							</div>
							
							<div>
								<a href="/" class="h-10 px-6 tracking-wide inline-flex items-center justify-center font-medium rounded-md bg-teal-500 text-white w-full">Free Trial</a>
							</div>
						</div>
					</form>
				</div>
			</div>
		</div>
	</div>
</section>