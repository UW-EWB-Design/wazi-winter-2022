<template>
	<!-- Filter Dropdown -->
	<div class="relative">
		<!-- Button -->
		<button
			class="buttonWidth flex justify-between rounded-sm w-max h-10 px-4 py-2 mt-2 mx-5 border border-black duration-300 hover:bg-gray-100"
			v-bind:class="this.zIndex"
			aria-controls="filter-menu"
			aria-expanded="false"
			@click="isOpen = !isOpen"
		>
			<p>
				{{ action }}
				<b>{{ selected }} {{ description }}</b>
			</p>
			<svg class="ml-3 h-5 w-5 ml-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
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
				class="px-5 absolute w-full rounded-sm cursor-pointer text-sm font-bold"
				v-bind:class="this.zIndex"
				role="menu"
				aria-orientation="vertical"
				aria-labelledby="filter-menu"
			>
				<ul>
					<!-- List of options -->
					<li v-for="option in options" :key="option">
						<a
							class="block px-4 py-2 bg-white hover:bg-gray-100 border border-black border-t-0 duration-300"
							role="menuitem"
							@click="filter(option)"
							>{{ option }}</a
						>
					</li>
				</ul>
			</div>
		</transition>
	</div>
</template>

<script>
export default {
	name: "Dropdown",
	props: { selected: String, description: String, action: String, isOpen: Boolean, options: Array, zIndex: String },
	methods: {
		filter(option) {
			this.$emit("filter", option);
		},
	},
};
</script>

<style scoped>
.buttonWidth {
	width: -moz-available;
	width: -webkit-fill-available;
	width: fill-available;
}
</style>
