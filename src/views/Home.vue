<template>
	<div class="home">
		<div class="p-4">
			<h1 class="text-blue-500">This is the home page</h1>
			<Sessions :sessions="sessions"/>
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
                    notes: "Reason/Additional Note for Session"
                },
                {
                    therapist: "Dr.Lee",
                    datetime: "2021-11-04T21:53:22+00:00",
                    notes: "Reason/Additional Note for Session"
                },
                {
                    therapist: "Dr.Doctor",
                    datetime: "2021-11-04T21:53:22+00:00",
                    notes: "Reason/Additional Note for Session"
                },
            ]
        }
    }
};
</script>
