<template>
<button class="AssessmentButton w-full">
  <span class="text-lg leading-tight
						 ">+</span><slot>Take an Assessment</slot>
</button>
</template>

<script>

export default {
  name: "AssessmentButton",
}
</script>

<style scoped>
.AssessmentButton {
  background: white;
  border: orange 2px solid;
  color: orange;
  cursor: pointer;
  font-size: 0.75rem;
  padding: 10px 25px;
  transition-duration: 0.4s;
  font-weight: 700;
  font-size: 15px;
}

.AssessmentButton:hover {
  background-color: orange;
  color: black;
}

span {
  float: left;
  left: -14px;
  position: relative;
}


</style>