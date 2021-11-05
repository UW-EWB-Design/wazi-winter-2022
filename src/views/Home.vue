<template>
	<div class="home">
		<div class="p-4">
			<h1 class="text-blue-500">This is the home page</h1>
			<Sessions :sessions="sessions" :userTherapists="userTherapists" />
		</div>
	</div>
</template>

<script>
import Sessions from "../components/sessions/Sessions.vue";

export default {
	name: "Home",
	components: { Sessions },
	data() {
		return {
			sessions: [
				{
					therapist: "Dr.Smith",
					datetime: "2021-11-04T21:53:22+00:00",
					notes: "Reason/Additional Note for Session",
                    completed: true,
                    id: 1,
				},
                {
					therapist: "Dr.Lee",
					datetime: "2021-11-04T21:53:22+00:00",
					notes: "Reason/Additional Note for Session",
                    completed: true,
                    id: 2,
				},
                {
					therapist: "Dr.Lee",
					datetime: "2021-11-04T21:53:22+00:00",
					notes: "Reason/Additional Note for Session",
                    completed: false,
                    id: 3,
				},
                {
					therapist: "Dr.Lee",
					datetime: "2021-11-04T21:53:22+00:00",
					notes: "Reason/Additional Note for Session",
                    completed: false,
                    id: 4,
				},
                {
					therapist: "Dr.Lee",
					datetime: "2021-11-04T21:53:22+00:00",
					notes: "Reason/Additional Note for Session",
                    completed: false,
                    id: 5,
				},{
					therapist: "Dr.Lee",
					datetime: "2021-11-04T21:53:22+00:00",
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
            ]
		};
	},
};
</script>
