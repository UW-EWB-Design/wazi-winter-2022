<template>
    <div class="AddAssessmentButton">
        <div class="w-48 mx-auto my-2 p-3 rounded-full bg-blue-500 text-white hover:bg-blue-300">
            <button>+ Assessment</button>
        </div>
        
    </div>
</template>

<script>
export default {
	name: "AddAssessmentButton",
	props: { assessment: Object },
    data() {
		return {
			
		};
	},
};
</script>