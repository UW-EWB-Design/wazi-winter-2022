<template>
	<div class="w-full flex justify-center">
		<!-- Advanced Filter button: Opens modal -->
		<button class="relative font-bold rounded-sm w-24 py-2 my-2 h-10 border border-black duration-300 hover:bg-gray-100">
			<span class="absolute left-3 text-lg leading-tight">+</span>Filter
		</button>
		<!-- Filter Dropdown -->
		<div class="relative w-max">
			<!-- Button -->
			<button
				class="z-50 flex rounded-sm h-10 px-4 py-2 mt-2 mx-5 border border-black duration-300 hover:bg-gray-100"
				aria-controls="filter-menu"
				aria-expanded="false"
				@click="isOpen = !isOpen"
			>
				<p>View <b>{{assessmentFilter}} Assessments</b></p>
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
					class="px-5 absolute w-full rounded-sm cursor-pointer text-sm font-bold bg-white "
					role="menu"
					aria-orientation="vertical"
					aria-labelledby="filter-menu"
				>
					<a class="block px-4 py-2 hover:bg-gray-100 border border-black border-t-0 duration-300" role="menuitem" @click="filter('all')">All</a>
					<a class="block px-4 py-2 hover:bg-gray-100 border border-black border-t-0 duration-300" role="menuitem" @click="filter('high')">High</a>
					<a class="block px-4 py-2 hover:bg-gray-100 border border-black border-t-0 duration-300" role="menuitem" @click="filter('moderate')">Moderate</a>
					<a class="block px-4 py-2 hover:bg-gray-100 border border-black border-t-0 duration-300" role="menuitem" @click="filter('low')">Low</a>
				</div>
			</transition>
		</div>
	</div>
</template>

<script>
export default {
	data: () => ({
        assessmentFilter:'All',
		isOpen: false,
	}),
	methods: {
		filter(option) {
            this.isOpen = false;
			// Pass selected filter to parent component
			if (option === "high") {
                // Sets local state
                this.assessmentFilter = "High";
                // Passes state to parent
				this.$emit("filter", "high");
				
			} else if (option === "moderate") {
                this.assessmentFilter = "Moderate";
				this.$emit("filter", "moderate");
			} else if (option === "low") {
                this.assessmentFilter = "Low";
				this.$emit("filter", "low");
			} else {
                this.assessmentFilter = "All";
				this.$emit("filter", "all");
			}
		},
	},
};
</script>
