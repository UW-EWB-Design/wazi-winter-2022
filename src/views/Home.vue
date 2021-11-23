<template>
	<div class="home">
		<div class="p-4">
			<!-- <h1 class="text-blue-500">This is the home page</h1> -->
			<Assessments :assessments="assessments" />
			<div class="h-12"></div>
			<Sessions :sessions="sessions" :userTherapists="userTherapists" />
		</div>
	</div>
</template>

<script>
import Sessions from "../components/HomePage/sessions/Sessions.vue";
import Assessments from "../components/HomePage/assessments/Assessments.vue";

export default {
	name: "Home",
	components: {
		Sessions,
		Assessments,
	},
	data() {
		return {
			sessions: [
				{
					therapist: "Dr.Smith",
					datetime: "2021-11-12T05:02:29+0000",
					notes: "Reason/Additional Note for Session",
					completed: true,
					id: 1,
				},
				{
					therapist: "Dr.Lee",
					datetime: "2021-10-13T05:02:29+0000",
					notes: "Reason/Additional Note for Session",
					completed: true,
					id: 2,
				},
				{
					therapist: "Dr.Lee",
					datetime: "2021-11-12T05:02:29+0000",
					notes: "Reason/Additional Note for Session",
					completed: false,
					id: 3,
				},
				{
					therapist: "Dr.Lee",
					datetime: "2021-10-01T05:02:29+0000",
					notes: "Reason/Additional Note for Session",
					completed: false,
					id: 4,
				},
				{
					therapist: "Dr.Lee",
					datetime: "2021-11-12T05:02:29+0000",
					notes: "Reason/Additional Note for Session",
					completed: false,
					id: 5,
				},
				{
					therapist: "Dr.Lee",
					datetime: "2021-11-12T05:02:29+0000",
					notes: "Reason/Additional Note for Session",
					completed: false,
					id: 6,
				},
			],
			userTherapists: [
				{
					name: "Smith",
				},
				{
					name: "Lee",
				},
				{
					name: "John",
				},
			],
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
};
</script>
