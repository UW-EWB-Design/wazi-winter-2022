<template>
	<transition name="modal">
		<div class="fixed z-50 top-0 left-0 w-full h-full bg-black bg-opacity-50 transition-opacity duration-300 ease-in-out">
			<div class="align-top pt-24">
				<div class="w-96 h-auto text-sm shadow shadow-xl mx-auto pt-5 bg-white rounded-sm transition-all duration-300 ease-in-out">
					<div class="p-2">
						<p class="pb-2">Assessments</p>
						<p class="text-xl font-semibold">Advanced Filters</p>
						<div class="text-left my-5">
							<!-- TO DO: Extract the duplicated classes -->
							<!-- Filter 1 -->
							<div class="mt-5">
								<p class="ml-5">Assessment Name</p>
								<!-- Dropdown -->
								<div class="dropdown dropdown1 dropdown-container relative">
									<!-- Button -->
									<button
										class="
											dropdown
											dropdown1
											dropdown-button
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
										@click.prevent="filterProps1.isOpen = !filterProps1.isOpen"
									>
										<p class="dropdown dropdown1 dropdown-text">
											View
											<b class="dropdown dropdown1 dropdown-text">{{ filterProps1.selected }} Assessments</b>
										</p>
										<!-- Arrow -->
										<svg
											class="dropdown dropdown2 dropdown-icon ml-3 h-5 w-5 ml-2"
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
									<Dropdown
										:id="filterProps1.id"
										:selected="filterProps1.selected"
										:isOpen="filterProps1.isOpen"
										:options="filterProps1.options"
										v-on:filter="onFilter1"
									/>
								</div>
							</div>
							<!-- Filter 2 -->
							<div class="mt-5">
								<p class="ml-5">Sort By</p>
								<div class="dropdown dropdown2 dropdown-container relative">
									<!-- Button -->
									<button
										class="
											dropdown
											dropdown2
											dropdown-button
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
										@click.prevent="filterProps2.isOpen = !filterProps2.isOpen"
									>
										<p class="dropdown dropdown2 dropdown-text">
											Sort by
											<b class="dropdown dropdown2 dropdown-text">{{ filterProps2.selected }}</b>
										</p>
										<!-- Arrow -->
										<svg
											class="dropdown dropdown2 dropdown-icon ml-3 h-5 w-5 ml-2"
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
									<Dropdown
										:id="filterProps2.id"
										:selected="filterProps2.selected"
										:options="filterProps2.options"
										:isOpen="filterProps2.isOpen"
										v-on:filter="onFilter2"
									/>
								</div>
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
								<div class="dropdown dropdown3 dropdown-container relative">
									<!-- Button -->
									<button
										class="
											dropdown
											dropdown3
											dropdown-button
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
										@click.prevent="filterProps3.isOpen = !filterProps3.isOpen"
									>
										<p class="dropdown dropdown3 dropdown-text">
											View
											<b class="dropdown dropdown3 dropdown-text">{{ filterProps3.selected }} Labels</b>
										</p>
										<!-- Arrow -->
										<svg
											class="dropdown dropdown3 dropdown-icon ml-3 h-5 w-5 ml-2"
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
									<Dropdown
										:id="filterProps3.id"
										:selected="filterProps3.selected"
										:options="filterProps3.options"
										:isOpen="filterProps3.isOpen"
										v-on:filter="onFilter3"
									/>
								</div>
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
			id: "dropdown1",
			selected: "All",
			isOpen: false,
			options: ["Name1", "Name2", "Name3"],
		},
		filterProps2: {
			type: "Sort",
			id: "dropdown2",
			selected: "Recent",
			isOpen: false,
			options: ["Recent", "Recommended"],
		},
		filterProps3: {
			type: "Label",
			id: "dropdown3",
			selected: "All",
			isOpen: false,
			options: ["All", "Low", "Moderate", "High"],
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
		close(e) {
			if (!e.target.classList.contains("dropdown1")) {
				this.filterProps1.isOpen = false;
			}
			if (!e.target.classList.contains("dropdown2")) {
				this.filterProps2.isOpen = false;
			}
			if (!e.target.classList.contains("dropdown3")) {
				this.filterProps3.isOpen = false;
			}
		},
	},
	mounted() {
		document.addEventListener("click", this.close);
	},
	beforeDestroy() {
		document.removeEventListener("click", this.close);
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
