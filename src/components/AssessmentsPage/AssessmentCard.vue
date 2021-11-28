<template>
	<div class="AssessmentCard">
		<div class="w-full text-left text-sm border border-gray-200 hover:bg-gray-100 cursor-pointer">
			<div class="p-4">
				<div class="flex flex-row justify-between">
					<b class="w-5/6">{{ assessment.name }}</b>
					<div class="flex justify-around w-1/6">
						<p>{{ date }}</p>
						<p class="text-gray-400 hover:text-blue-800" href="#">></p>
					</div>
					
				</div>
				
				<p class="text-gray-400 text-xs w-5/6">{{assessment.description}}</p>
				<p class="text-gray-400 text-xs mt-5 font-semibold	"><span v-bind:class="classObject">{{level}}</span> Stress</p>
				
			</div>
			
		</div>
	</div>
</template>

<script>
export default {
	name: "AssesmentCard",
	props: { assessment: Object },
    data() {
		return {
			level: this.assessment.level,
		};
	},
    computed: {
		date: function () {
            // Assuming datetime is given in ISO format
            let options = {  month: 'short', day: 'numeric' };
			let date = new Date(this.assessment.datetime);
			return date.toLocaleDateString('en-US', options);
		},
        classObject: function () {
            return {
                'text-red-500': this.assessment.level == "High",
                'text-yellow-400': this.assessment.level == "Moderate",
                'text-green-500': this.assessment.level == "Low",
            }
        }
	},
};
</script>
