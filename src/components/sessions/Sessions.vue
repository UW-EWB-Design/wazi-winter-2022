<template>
	<div class="Sessions">
		<div class="max-w-md mx-auto shadow-md border-2 border-gray-100 rounded shadow-md overflow-hidden md:max-w-2xl md:flex">
			<div class="p-4">
				<div class="text-left text-base">Sessions</div>
				<!-- No sessions -->
				<div v-if="totalSessions === 0" class="p-5 text-sm">
					<p>You have not had any sessions. Speak with a licensed therapist today!</p>
				</div>
				<!-- Existing sessions -->
				<div v-else>
					<div class="flex flex-row justify-between my-4">
						<!-- Session Stats -->
						<div class="flex-col content-center h-24 w-36 p-2 border border-gray-200">
							<p class="text-3xl">{{ completedSessions }}</p>
							<p class="text-sm text-center">Therapy Sessions Completed</p>
						</div>
						<div class="flex-col content-center h-24 w-36 p-2 px-4 border border-gray-200">
							<p class="text-3xl">{{ therapists }}</p>
							<p class="text-sm text-center">Therapists Spoken To</p>
						</div>
					</div>
				</div>
				<!-- Book a session -->
				<button class="relative font-bold rounded px-6 py-2 my-2 w-full border border-blue-700 text-blue-700 hover:bg-blue-600 hover:text-white">
					<span class="absolute left-4 text-lg leading-tight">+</span>Book a Session
				</button>
			</div>
			<!-- Recent Sessions -->
			<div v-if="totalSessions > 0" class="pb-2 pr-2">
				<div class="pb-2 px-4 text-xs text-left">Recent Sessions</div>
				<div class="w-full h-auto bg-gray-400">
					<!-- Get top 3 recent sessions -->
					<ul>
						<li v-for="session in sessions" :key="session.id">
							<DemoSessionCard :session="session" />
						</li>
					</ul>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import DemoSessionCard from "./DemoSessionCard.vue";
export default {
	name: "Sessions",
	props: { sessions: Array },
	components: { DemoSessionCard },
	data() {
		return {
			totalSessions: 0,
			completedSessions: 24,
			therapists: 3,
		};
	},
};
</script>
