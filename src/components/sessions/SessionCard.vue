<template>
	<div class="SessionCard">
		<div class="w-full text-left text-sm border border-gray-200 hover:bg-gray-100 cursor-pointer">
			<div class="border-l-2 border-blue-800 p-4">
				<div class="flex flex-row justify-between">
					<b>{{ session.therapist }} - {{session.time}} Session</b>
					<div class="flex justify-around w-1/6">
						<p>{{session.date}}</p>
						<p class="text-gray-400 hover:text-blue-800">></p>
					</div>
					
				</div>
				
				<p class="text-gray-400 text-xs">{{session.notes}}</p>
			
				
			</div>
			
		</div>
	</div>
</template>

<script>
export default {
	name: "SessionCard",
	props: { session: Object },
};
</script>
