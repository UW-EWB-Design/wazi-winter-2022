<template>
	<div class="w-full flex justify-center">
		<!-- Advanced Filter button: Opens modal -->
		<button class="relative font-bold rounded-sm w-24 py-2 my-2 h-10 border border-black duration-300 hover:bg-gray-100" @click="showModal = true">
			<span class="absolute left-3 text-lg leading-tight">+</span>Filter
		</button>
		<!-- Advanced Filter Modal -->
		<FilterModal v-if="showModal" @close="showModal = false" v-on:filter="advancedFilter" />
		<!-- Dropdown -->
		<Dropdown
			:selected="filterProps.selected"
			:action="filterProps.action"
			:description="filterProps.description"
			:options="filterProps.options"
			:zIndex="filterProps.zIndex"
			v-on:filter="filter"
		/>
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
			action: "View",
			description: "Assessments",
			options: ["All", "Low", "Moderate", "High"],
			zIndex: "z-50",
		},
		showModal: false,
	}),
	methods: {
		filter(option) {
			this.filterProps.selected = option;
			this.$emit("filter", option);
		},
		advancedFilter(option) {
			this.$emit("advancedFilter", option);
		},
	},
};
</script>
