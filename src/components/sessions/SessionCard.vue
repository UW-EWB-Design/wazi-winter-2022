<template>
	<div class="SessionCard">
		<div class="w-full text-left text-sm border border-gray-200 hover:bg-gray-100 cursor-pointer">
			<div class="border-l-2 border-blue-800 p-4">
				<div class="flex flex-row justify-between">
					<b>{{ session.therapist }} - {{ time }} Session</b>
					<div class="flex justify-around w-1/6">
						<p>{{ date }}</p>
						<p class="text-gray-400 hover:text-blue-800" href="#">></p>
					</div>
				</div>

				<p class="text-gray-400 text-xs">{{ session.notes }}</p>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: "SessionCard",
	props: { session: Object },
	computed: {
		date: function () {
            // Assuming datetime is given in ISO format
            let options = {  month: 'short', day: 'numeric' };
			let date = new Date(this.session.datetime);
			return date.toLocaleDateString('en-US', options);
		},
		time: function () {
            // Assuming datetime is given in ISO format
            let options = { hour: 'numeric', minute: "numeric"};
            let time = new Date(this.session.datetime);
			return time.toLocaleTimeString('en-US', options);
		},
	},
};
</script>
