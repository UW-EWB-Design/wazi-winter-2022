<template>
	<div class="DemoSessionCard">
		<div class="w-full bg-blue-100 h-12">
			<p>{{ session.therapist }}</p>
		</div>
	</div>
</template>

<script>
export default {
	name: "DemoSessionCard",
	props: { session: Object },
};
</script>
