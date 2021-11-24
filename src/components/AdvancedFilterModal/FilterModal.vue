<template>
	<transition name="modal">
		<div class="fixed z-50 top-0 left-0 w-full h-full bg-black bg-opacity-50 transition-opacity duration-300 ease-in-out">
			<div class="align-top pt-24">
				<div class="w-96 h-auto shadow shadow-xl mx-auto pt-5 bg-white rounded-sm transition-all duration-300 ease-in-out">
					<div class="mt-0">
						<p class="text-2xl font-medium">Advanced Filters</p>
					</div>
					<div class="text-left mt-2">
						<!-- Filter 1 -->
						<div class="mt-5">
							<p class="ml-5">Assessment Name</p>
							<Dropdown :selectedFilter="filter1" :isOpen="openFilter1" :filterOptions="filter1Options" v-on:filter="onFilter1" />
						</div>
						<!-- Filter 2 -->
						<div class="mt-5">
							<p class="ml-5">Sort By</p>
							<Dropdown :selectedFilter="filter2" :isOpen="openFilter2" :filterOptions="filter2Options" v-on:filter="onFilter2" />
						</div>
						<!-- Date Filtering -->
						<div class="mt-5">
							<p class="ml-5">Dates</p>
							<p class="ml-5">From</p>
							<p class="ml-5">To</p>
						</div>
						<!-- Filter 3 -->
						<div class="mt-5">
							<p class="ml-5">Severity of Result</p>
							<Dropdown :selectedFilter="filter3" :isOpen="openFilter3" :filterOptions="filter3Options" v-on:filter="onFilter3" />
						</div>
					</div>
					<div class="my-5 py-5 flex justify-around">
						<button class="text-sm" @click="$emit('close')">Cancel</button>
						<button class="border py-2 px-3 rounded-md bg-blue-500 text-sm text-white" @click="$emit('close')">Apply</button>
					</div>
				</div>
			</div>
		</div>
	</transition>
</template>

<script>
import Dropdown from "./dropdown.vue";

export default {
	data: () => ({
		filter1: "All",
		openFilter1: false,
		filter1Options: ["Name1", "Name2", "Name3"],
		filter2: "Recent",
		openFilter2: false,
		filter2Options: ["Recent", "Recommended"],
		filter3: "All",
		openFilter3: false,
		filter3Options: ["All", "Low", "Moderate", "High"],
	}),
	components: {
		Dropdown,
	},
	methods: {
		onFilter1(option) {
			this.filter1 = option;
			this.$emit("filter", option);
		},
		onFilter2(option) {
			this.filter2 = option;
			this.$emit("filter", option);
		},
		onFilter3(option) {
			this.filter3 = option;
			this.$emit("filter", option);
		},
	},
};
</script>
