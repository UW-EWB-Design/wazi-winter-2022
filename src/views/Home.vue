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
					date: "Mar 1",
					time: "3 PM",
					notes: "Reason/Additional Note for Session",
                    completed: true,
                    id: 1,
				},
                {
					therapist: "Dr.Lee",
					date: "Feb 22",
					time: "1 PM",
					notes: "Reason/Additional Note for Session",
                    completed: true,
                    id: 2,
				},
                {
					therapist: "Dr.Lee",
					date: "Jan 23",
					time: "7 PM",
					notes: "Reason/Additional Note for Session",
                    completed: false,
                    id: 3,
				},
                {
					therapist: "Dr.Lee",
					datetime: "Dec 23",
					time: "2 PM",
					notes: "Reason/Additional Note for Session",
                    completed: false,
                    id: 4,
				},
                {
					therapist: "Dr.Lee",
					datetime: "Dec 8",
					time: "4 PM",
					notes: "Reason/Additional Note for Session",
                    completed: false,
                    id: 5,
				},{
					therapist: "Dr.Lee",
					datetime: "Nov 7",
					time: "7 PM",
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
