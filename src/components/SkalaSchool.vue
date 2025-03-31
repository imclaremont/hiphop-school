<template>
    <div class="container">
      <h1>Welcome to My Hiphop🎤 School</h1>
      <div class="course-list">
        <SkalaCourse
          v-for="(course, index) in courses"
          :key="index"
          :title="course.title"
          :time="course.time"
          @start="handleStart"
        />
      </div>
      <p v-if="currentCourse" class="announcement">
        The course <strong>{{ currentCourse }}</strong> has started!
      </p>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import SkalaCourse from './SkalaCourse.vue'

const courses = ref([
  { title: 'Rapping', time: 10 },
  { title: 'Rhyming', time: 15 },
  { title: 'Punch-Line', time: 8 }
])

const currentCourse = ref('')

function handleStart(courseTitle) {
  currentCourse.value = courseTitle
}
</script>

<style scoped>
.container {
  max-width: 600px;
  margin: 3rem auto;
  text-align: center;
  font-family: 'Arial', sans-serif;
}

.course-list {
  margin-top: 2rem;
}

.announcement {
  margin-top: 2rem;
  color: #2ecc71;
  font-weight: bold;
}
</style>
  