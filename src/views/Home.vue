<template>
	<div class="home">
		<div class="p-4">
			<h1 class="text-blue-500">This is the home page</h1>
			<Sessions />
		</div>
	</div>
</template>

<script>
import Sessions from "../components/sessions/Sessions.vue";

export default {
	name: "Home",
	components: { Sessions },
};
</script>
