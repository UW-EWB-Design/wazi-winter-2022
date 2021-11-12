<template>
	<div class="w-full flex justify-center">
		<!-- Advanced Filter button: Opens modal -->
		<button class="relative font-bold rounded-sm w-24 py-2 my-2 border border-black duration-300 hover:bg-gray-100 cursor-pointer">
			<span class="absolute left-3 text-lg leading-tight">+</span>Filter
		</button>
		<!-- Filter Dropdown -->
		<div class="relative inline-block">
			<!-- Button -->
			<button
				class="flex justify-center rounded-sm border px-4 py-2 mt-2 mx-5 w-64 border-black duration-300 hover:bg-gray-100"
				aria-controls="filter-menu"
				aria-expanded="false"
				@click="isOpen = !isOpen"
			>
				<p>View <b>All Assessments</b></p>
				<svg class="h-5 w-5 ml-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
					<path
						fill-rule="evenodd"
						d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
						clip-rule="evenodd"
					/>
				</svg>
			</button>
			<!-- Filter Dropdown -->
			<transition
				enter-active-class="transition ease-out duration-100 transform"
				enter-class="opacity-0 scale-95"
				enter-to-class="opacity-100 scale-100"
				leave-active-class="transition ease-in duration-75 transform"
				leave-class="opacity-100 scale-100"
				leave-to-class="opacity-0 scale-95"
			>
				<div
					v-show="isOpen"
					class="z-10 mx-5 absolute w-64 rounded-sm focus:outline-none cursor-pointer text-sm font-bold"
					role="menu"
					aria-orientation="vertical"
					aria-labelledby="filter-menu"
				>
                    <a class="block px-4 py-2  hover:bg-gray-100 border border-black border-t-0" role="menuitem" @click="filter('All')">All</a>
					<a class="block px-4 py-2 hover:bg-gray-100 border border-black border-t-0" role="menuitem" @click="filter('option1')">High</a>
					<a class="block px-4 py-2 hover:bg-gray-100 border border-black border-t-0" role="menuitem" @click="filter('option2')">Moderate</a>
					<a class="block px-4 py-2 hover:bg-gray-100 border border-black border-t-0" role="menuitem" @click="filter('option3')">Low</a>
				</div>
			</transition>
		</div>
	</div>
</template>

<script>
export default {
	data: () => ({
		isOpen: false,
	}),
    methods: {
        filter(option) {
            // Filter array
            if (option === 'All') {

            } else if (option === 'All') {

            } else if (option === 'All') {

            } else {

            }
        }
    }
};
</script>
