<script setup>
import {ref} from 'vue';
const dataProps = defineProps({
  rendered : Boolean
})

const item = ref([{name: 'Project 1'}, {name: 'Project 2'}, {name: 'Project 3'}]);

const anotherTransition = ref(false);
function setTransitionState() {
  anotherTransition.value = !anotherTransition.value;
}
</script>

<template>
  <div class="projectsDiv">
    <Transition>
      <div v-if="rendered">
        <h2>Projects</h2>
        <TransitionGroup name="projectList" tag="ul">
          <li v-for="project in item">
            {{ project.name }}
          </li>
        </TransitionGroup>
      </div>
    </Transition>
  </div>
</template>

<style>
.projectsDiv {
  width: 400px;
  height: 400px;
}

.projectList-enter-active,
.projectList-leave-active {
  transition: all 0.5s ease;
}

.projectList-enter-from,
.projectList-leave-to {
  opacity: 0;
  transform: translateX(30px);
}

.v-enter-active,
.v-leave-active {
  transition: opacity 1s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>