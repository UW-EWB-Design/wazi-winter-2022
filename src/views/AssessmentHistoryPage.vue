<template>
	<div class="assessment-history">
		<Toolbar v-on:filter="filter" />
        <!-- Here for testing (remove after): -->
        <p >{{assessmentFilter}}</p>
	</div>
</template>

<script>
import Toolbar from "../components/AssessmentsPage/Toolbar.vue";
export default {
	name: "AssessmentHistory",
    data() {
        return {
            // Pass to card list to use for filtering
            assessmentFilter: 'all',
        };
    },
	components: {
		Toolbar,
	},
    methods: {
        filter(option) {
            this.assessmentFilter = option;
        }
    }
};
</script>
