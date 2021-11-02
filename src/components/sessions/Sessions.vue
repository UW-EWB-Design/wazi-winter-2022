<template>
	<div class="Sessions">
		<div class="shadow-md border-2 border-gray-100 rounded w-96 h-80 mx-auto my-8 md:w-80 p-5">
			<div class="text-left">
				<h1 class="text-base">Sessions</h1>
			</div>
			<div class="flex flex-row justify-evenly my-4">
				<div class="flex-col justify-between h-32 w-40 p-4 border-2 border-gray-100">
                    <p class="text-3xl">24</p>
					<p class="text-sm">Therapy Sessions Completed</p>
				</div>
				<div class="flex-col justify-between h-32 w-40 p-4 border-2 border-gray-100">
                    <p class="text-3xl">3</p>
					<p class="text-sm">Therapists Spoken To</p>
				</div>
			</div>
			<button class="text-base font-bold border-2 border-blue-700 text-blue-700 rounded px-6 py-2 w-11/12">Book a Session</button>
            <div class="py-5">
                <p class="text-xs text-left">Recent Sessions</p>
            </div>
		</div>
	</div>
</template>

<script>
export default {
	name: "Sessions",
};
</script>
