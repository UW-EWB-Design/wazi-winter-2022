<template>
	<div class="assessment-history">
		<Toolbar v-on:filter="filter" v-on:advancedFilter="advancedFilter" />
		<!-- Here for testing (remove after): -->
		<p>{{ assessmentFilter }}</p>
		<p>{{ advancedFilters }}</p>
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
		advancedFilter(option) {
			this.advancedFilters = option;
		},
	},
};
</script>
