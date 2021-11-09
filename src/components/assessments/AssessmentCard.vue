<template>
	<div class="AssessmentCard">
		<div class="w-full text-left text-sm border border-gray-200 hover:bg-gray-100 cursor-pointer">
			<div class="border-l-2 border-blue-800 p-4">
				<div class="flex flex-row justify-between">
					<b>{{ assessment.name }}</b>
					<div class="flex justify-around w-1/6">
						<p>{{ assessment.dateTime }}</p>
						<p class="text-gray-400 hover:text-blue-800" href="#">></p>
					</div>
					
				</div>
				
				<p class="text-gray-400 text-xs">{{assessment.description}}</p>
				<p class="text-gray-400 text-xs">{{assessment.level}} Stress</p>
				
			</div>
			
		</div>
	</div>
</template>

<script>
export default {
	name: "AssesmentCard",
	props: { assessment: Object }
};
</script>
