<template>
	<div class="Sessions">
		<div class="max-w-md mx-auto shadow-md border-2 border-gray-100 rounded shadow-md overflow-hidden md:max-w-2xl md:flex">
			<div class="p-4">
				<div class="text-left text-base">Sessions</div>
				<div class="flex flex-row justify-between my-4">
                    <!-- Session Stats -->
					<div class="flex-col content-center h-24 w-36 p-2 border border-gray-200">
						<p class="text-3xl">24</p>
						<p class="text-sm text-center">Therapy Sessions Completed</p>
					</div>
					<div class="flex-col content-center h-24 w-36 p-2 px-4 border border-gray-200">
						<p class="text-3xl">3</p>
						<p class="text-sm text-center">Therapists Spoken To</p>
					</div>
				</div>
				<button class="relative font-bold rounded px-6 py-2 w-full border border-blue-700 text-blue-700 hover:bg-blue-600 hover:text-white">
					<span class="absolute left-4 text-lg leading-tight">+</span>Book a Session
				</button>
			</div>
			<div class="pt-5 px-4 text-xs text-left">Recent Sessions</div>
            <!-- Recent Sessions -->
			<div class="w-full h-32"></div>
		</div>
	</div>
</template>

<script>
export default {
	name: "Sessions",
};
</script>
