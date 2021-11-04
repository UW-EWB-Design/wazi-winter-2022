<template>
	<div class="home">
		<h1 class="text-blue-500">This is the home page</h1>
        <Script />
	</div>
</template>

<script>
import Sessions from '../components/sessions/Sessions.vue'

export default {
    name: "Home",
    components: {Sessions}
}
</script>