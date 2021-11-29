<template>
	<!-- Filter Dropdown -->

	<!-- Dropdown Options -->
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
			class="dropdown px-5 absolute w-full cursor-pointer text-sm font-medium"
			v-bind:class="zIndex"
			role="menu"
			aria-orientation="vertical"
			aria-labelledby="filter-menu"
		>
			<ul class="shadow-md rounded-sm">
				<!-- List of options -->
				<li v-for="option in options" :key="option">
					<a
						class="dropdown dropdown-option block px-4 py-2 bg-white hover:bg-gray-100 border border-black border-t-0 duration-300"
						role="menuitem"
						@click="filter(option)"
						>{{ option }}</a
					>
				</li>
			</ul>
		</div>
	</transition>
</template>

<script>
export default {
	name: "Dropdown",
	props: { selected: String, description: String, action: String, isOpen: Boolean, options: Array, zIndex: String },
	methods: {
		filter(option) {
			// passes to parent
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
