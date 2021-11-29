<template>
	<div class="w-full flex justify-center">
		<!-- Advanced Filter button: Opens modal -->
		<button class="relative font-bold rounded-sm w-24 py-2 my-2 h-10 border border-black duration-300 hover:bg-gray-100" @click="openModal">
			<span class="absolute left-3 text-lg leading-tight">+</span>Filter
		</button>
		<!-- Advanced Filter Modal -->
		<FilterModal v-if="showModal" @close="showModal = false" v-on:filter="advancedFilter" />
		<!-- Dropdown -->
		<div class="dropdown dropdown-container relative">
			<!-- Button -->
			<button
				class="
					dropdown dropdown-button
					buttonWidth
					flex
					justify-between
					rounded-sm
					w-max
					h-10
					px-4
					py-2
					mt-2
					mx-5
					border border-black
					duration-300
					hover:bg-gray-100
				"
				aria-controls="filter-menu"
				aria-expanded="false"
				@click.prevent="filterProps.isOpen = !filterProps.isOpen"
			>
				<p class="dropdown dropdown-text">
					View
					<b class="dropdown dropdown-text">{{ filterProps.selected }} Assessments</b>
				</p>
				<!-- Arrow -->
				<svg
					class="dropdown dropdown-icon ml-3 h-5 w-5 ml-2"
					xmlns="http://www.w3.org/2000/svg"
					viewBox="0 0 20 20"
					fill="currentColor"
					aria-hidden="true"
				>
					<path
						fill-rule="evenodd"
						d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
						clip-rule="evenodd"
					/>
				</svg>
			</button>
			<Dropdown :selected="filterProps.selected" :options="filterProps.options" :isOpen="filterProps.isOpen" v-on:filter="filter" />
		</div>
	</div>
</template>

<script>
import FilterModal from "../AdvancedFilterModal/FilterModal.vue";
import Dropdown from "../dropdown.vue";

export default {
	components: {
		FilterModal,
		Dropdown,
	},
	data: () => ({
		filterProps: {
			selected: "All",
			options: ["All", "Low", "Moderate", "High"],
			isOpen: false,
		},
		showModal: false,
	}),
	methods: {
		filter(option) {
			this.filterProps.isOpen = false;
			this.filterProps.selected = option;
			this.$emit("filter", option);
		},
		advancedFilter(option) {
			this.$emit("advancedFilter", option);
		},
		openModal() {
			this.filterProps.isOpen = false;
			this.showModal = true;
		},
		closeDropdown(e) {
			if (!e.target.classList.contains("dropdown")) {
				this.filterProps.isOpen = false;
			}
		},
	},
	mounted() {
		document.addEventListener("click", this.closeDropdown);
	},
	beforeDestroy() {
		document.removeEventListener("click", this.closeDropdown);
	},
};
</script>
