<template>
	<div class="assessment-history">
		<Toolbar v-on:filter="filter" v-on:advancedFilter="advancedFilter" />
		<!-- Here for testing (remove after): -->
		<p>Simple filtering selection: {{ assessmentFilter }}</p>
		<p>Advanced filtering selection: {{ advancedFilters }}</p>
	</div>
</template>

<script>
import Toolbar from "../components/AssessmentsPage/Toolbar.vue";
export default {
	name: "AssessmentHistory",
	data() {
		return {
			// Pass to card list to use for filtering
			assessmentFilter: "All",
			advancedFilters: "Advanced",
		};
	},
	components: {
		Toolbar,
	},
	methods: {
		filter(option) {
			this.assessmentFilter = option;
		},
		// TO DO: Get the option from all 3 filter selections as opposed to just 1
		advancedFilter(option) {
			this.advancedFilters = option;
		},
	},
};
</script>
