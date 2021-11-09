<template>
	<div class="Assessments">
		<div class="max-w-md mx-auto shadow-md border-2 border-gray-100 rounded-sm overflow-hidden md:max-w-2xl">
			<div class="p-4 w-full">
				<div class="text-left text-base pb-5">Assessments</div>
				<!-- No sessions -->
				<div v-if="totalAssessments === 0" class="pb-5 text-sm">
					<p>You have not taken any assessments yet.</p>
				</div>
				<!-- Take an Assessment -->
				<AssessmentButton />
			</div>
			<!-- Recent Sessions -->
			<div v-if="totalAssessments > 0" class="pb-2 pr-2 w-full">
				<div class="pb-2 px-4 text-sm text-left">Recent Assessments</div>
				<div class="flex flex-col h-5/6">
					<ul>
						<!-- List of assessments -->
						<li v-for="assessment in assessments" :key="assessment.id">
							<AssessmentCard :assessment="assessment" />
						</li>
					</ul>
				</div>
				<div class="pt-2">
					<a class="text-sm underline cursor-pointer hover:bold" href="#">See full history</a>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import AssessmentCard from "./AssessmentCard.vue";
import AssessmentButton from './AssessmentButton.vue'


export default {
	name: "Assessments",
	props: { assessments: Array },
	components: { 
        AssessmentCard,
        AssessmentButton
    },
	data() {
		return {
			totalAssessments: this.assessments.length,
		};
	},
	computed: {
		recentSessions: function () {
			// assuming sessions are sorted by date
			return this.assessments.slice(0, 3);
		},
	},
};
</script>
