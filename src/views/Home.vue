<template>
  <div class="home">
    <h1>This is the home page</h1>
    <Sessions />
  </div>
</template>

<script>
import Sessions from '../components/sessions/Sessions.vue'

export default {
    name: "Home",
    components: {Sessions}
}
</script>