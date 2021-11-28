<template>
	<div class="assessment-history ">
		<Toolbar v-on:filter="filter" v-on:advancedFilter="advancedFilter" />
		<!-- Here for testing (remove after): -->
		<p>Simple filtering selection: {{ assessmentFilter }}</p>
		<p>Advanced filtering selection: {{ advancedFilters }}</p>

		<div class="max-w-md mx-auto">
			<ul>
				<!-- List of assessments -->
				<li v-for="assessment in assessments" :key="assessment.id">
					<AssessmentCard :assessment="assessment"/>
				</li>
			</ul>
		</div>	

		<AddAssessmentButton/>
	</div>
</template>

<script>
import Toolbar from "../components/AssessmentsPage/Toolbar.vue";
import AssessmentCard from "../components/AssessmentsPage/AssessmentCard.vue";
import AddAssessmentButton from "../components/AssessmentsPage/AddAssessmentButton.vue";

export default {
	name: "AssessmentHistory",
	data() {
		return {
			// Pass to card list to use for filtering
			assessmentFilter: "All",
			advancedFilters: "Advanced",
			assessments: [
				{
					id: 1,
					name: "Coronavirus Anxiety Scale (CAS)",
					description: "Measures coronavirus-related anxiety",
					level: "High",
					datetime: "2021-11-12T05:02:29+0000",
				},
				{
					id: 2,
					name: "Coronavirus Anxiety Scale (CAS) This assessment has a very long name",
					description: "Measures coronavirus-related anxiety. This assessment has a very long description",
					level: "Low",
					datetime: "2021-11-12T05:02:29+0000",
				},
				{
					id: 3,
					name: "Coronavirus Anxiety Scale (CAS)",
					description: "Measures coronavirus-related anxiety",
					level: "Moderate",
					datetime: "2021-11-12T05:02:29+0000",
				},
				{
					id: 4,
					name: "Coronavirus Anxiety Scale (CAS)",
					description: "Measures coronavirus-related anxiety",
					level: "High",
					datetime: "2021-11-12T05:02:29+0000",
				},
				{
					id: 5,
					name: "Coronavirus Anxiety Scale (CAS)",
					description: "Measures coronavirus-related anxiety",
					level: "Moderate",
					datetime: "2021-11-12T05:02:29+0000",
				},
			],
		};
	},
	components: {
		Toolbar,
		AssessmentCard,
		AddAssessmentButton,
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
