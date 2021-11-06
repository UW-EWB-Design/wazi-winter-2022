<template>
	<div class="Sessions">
		<div class="max-w-md mx-auto shadow-md border-2 border-gray-100 rounded-sm overflow-hidden md:max-w-2xl">
			<div class="p-4 w-full">
				<div class="text-left text-base">Sessions</div>
				<!-- No sessions -->
				<div v-if="totalSessions === 0" class="p-5 text-sm">
					<p>You have not had any sessions. Speak with a licensed therapist today!</p>
				</div>
				<!-- Existing sessions -->
				<div v-else>
					<div class="flex flex-row justify-between my-4">
						<!-- Session Stats -->
						<div class="flex-col flex-1 rounded-sm content-center h-auto p-3 border border-gray-200 duration-300 hover:bg-gray-100 cursor-pointer">
							<p class="text-3xl">{{ completedSessions }}</p>
							<p class="text-sm text-center">Therapy Sessions Completed</p>
						</div>
						<div class="w-2 flex-shrink"></div>
						<div class="flex-col flex-1 rounded-sm content-center h-auto p-3 border border-gray-200 duration-300 hover:bg-gray-100 cursor-pointer">
							<p class="text-3xl">{{ therapists }}</p>
							<p class="text-sm text-center">Therapists Spoken To</p>
						</div>
					</div>
				</div>
				<!-- Book a session -->
				<button
					class="
						relative
						font-bold
						rounded-sm
						px-6
						py-2
						my-2
						w-full
						border border-blue-800
						text-blue-800
						duration-300
						hover:bg-blue-600 hover:text-white
						cursor-pointer
					"
				>
					<span class="absolute left-4 text-lg leading-tight">+</span>Book a Session
				</button>
			</div>
			<!-- Recent Sessions -->
			<div v-if="totalSessions > 0" class="pb-2 pr-2 w-full">
				<div class="pb-2 px-4 text-sm text-left">Recent Sessions</div>
				<div class="flex flex-col h-5/6">
					<ul>
						<!-- List of sessions -->
						<li v-for="session in recentSessions" :key="session.id">
							<SessionCard :session="session" />
						</li>
					</ul>
				</div>
				<div class="pt-2">
					<a class="text-sm underline cursor-pointer hover:bold" href="#">See all sessions</a>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import SessionCard from "./SessionCard.vue";
export default {
	name: "Sessions",
	props: { sessions: Array, userTherapists: Array },
	components: { SessionCard },
	data() {
		return {
			totalSessions: this.sessions.length,
			therapists: this.userTherapists.length,
		};
	},
	computed: {
		recentSessions: function () {
			// assuming sessions are sorted by date
			return this.sessions.slice(0, 3);
		},
		completedSessions: function () {
			return this.sessions.filter((session) => session.completed).length;
		},
	},
};
</script>
