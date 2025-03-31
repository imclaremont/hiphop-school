<template>
    <div class="course-card">
      <h2>{{ title }}</h2>
      <p>Duration: {{ time }} hours</p>
      <button @click="startCourse">Start Course</button>
    </div>
</template>

<script setup>
const props = defineProps({
  title: String,
  time: Number
})

const emit = defineEmits(['start'])

function startCourse() {
  emit('start', props.title)
}
</script>

<style scoped>
.course-card {
  border: 1px solid #ddd;
  padding: 1.5rem;
  margin: 1rem 0;
  text-align: center;
  border-radius: 10px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  background-color: #fff;
}

button {
  background-color: #2ecc71;
  color: white;
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #27ae60;
}
</style>
