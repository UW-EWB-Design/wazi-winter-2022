<template>
	<transition name="modal">
		<div class="fixed z-50 top-0 left-0 w-full h-full bg-black bg-opacity-50 transition-opacity duration-300 ease-in-out">
			<div class="align-top pt-24">
				<div class="w-96 h-auto text-sm shadow shadow-xl mx-auto pt-5 bg-white rounded-sm transition-all duration-300 ease-in-out">
					<div class="p-2">
						<p class="pb-2">Assessments</p>
						<p class="text-xl font-semibold">Advanced Filters</p>
						<div class="text-left my-5">
							<!-- TO DO: Close all other dropdowns when one dropdown is selected -->
							<!-- Filter 1 -->
							<div class="mt-5">
								<p class="ml-5">Assessment Name</p>
								<Dropdown
									:selected="filterProps1.selected"
									:action="filterProps1.action"
									:description="filterProps1.description"
									:isOpen="filterProps1.isOpen"
									:options="filterProps1.options"
									:zIndex="filterProps1.zIndex"
									v-on:filter="onFilter1"
								/>
							</div>
							<!-- Filter 2 -->
							<div class="mt-5">
								<p class="ml-5">Sort By</p>
								<Dropdown
									:selected="filterProps2.selected"
									:action="filterProps2.action"
									:description="filterProps2.description"
									:options="filterProps2.options"
									:zIndex="filterProps2.zIndex"
									:isOpen="filterProps2.isOpen"
									v-on:filter="onFilter2"
								/>
							</div>
							<!-- Date Filtering -->
							<!-- TO DO: Replace with a Date selector and turn into dynamic values -->
							<div class="mt-10 ml-5">
								<p class="mb-2">Dates</p>
								<p>From:</p>
								<p class="font-bold">Wednesday, June 2</p>
								<p class="mt-2">To:</p>
								<p class="font-bold">Wednesday, June 3</p>
							</div>
							<!-- Filter 3 -->
							<div class="mt-10">
								<p class="ml-5">Label - Severity of Result</p>
								<Dropdown
									:selected="filterProps3.selected"
									:action="filterProps3.action"
									:description="filterProps3.description"
									:options="filterProps3.options"
									:zIndex="filterProps3.zIndex"
									:isOpen="filterProps3.isOpen"
									v-on:filter="onFilter3"
								/>
							</div>
						</div>
						<!-- Buttons -->
						<!-- TO DO: Add functionality to each button (cancel will cancel filters...)-->
						<div class="mt-10 flex justify-around">
							<button class="p-3 w-1/2 hover:bg-gray-100 duration-300" @click="$emit('close')">Cancel</button>
							<button class="p-3 w-1/2 hover:bg-gray-100 duration-300" @click="$emit('close')">Apply</button>
						</div>
					</div>
				</div>
			</div>
		</div>
	</transition>
</template>

<script>
import Dropdown from "../dropdown.vue";

export default {
	components: {
		Dropdown,
	},
	data: () => ({
		// Objects that pass properties to dropdown component to describe the behaviour
		filterProps1: {
			type: "Name",
			selected: "All",
			action: "",
			description: "Assessments",
			isOpen: false,
			options: ["Name1", "Name2", "Name3"],
			zIndex: "z-50",
		},
		filterProps2: {
			type: "Sort",
			selected: "Recent",
			action: "",
			description: "",
			isOpen: false,
			options: ["Recent", "Recommended"],
			zIndex: "z-40",
		},
		filterProps3: {
			type: "Label",
			selected: "All",
			action: "",
			description: "Labels",
			isOpen: false,
			options: ["All", "Low", "Moderate", "High"],
			zIndex: "z-30",
		},
	}),
	methods: {
		// Different filtering method for each filter
		onFilter1(option) {
			this.filterProps1.selected = option;
			this.$emit("filter", option);
		},
		onFilter2(option) {
			this.filterProps2.selected = option;
			this.$emit("filter", option);
		},
		onFilter3(option) {
			this.filterProps3.selected = option;
			this.$emit("filter", option);
		},
	},
	// mounted() {
	// 	document.addEventListener("click", (this.filterProps.isOpen = false));
	// },
	// beforeDestroy() {
	// 	document.removeEventListener("click", (this.filterProps.isOpen = false));
	// },
};
</script>
