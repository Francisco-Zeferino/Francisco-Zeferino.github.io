<script setup>
const dataProps = defineProps({
  rendered : Boolean
})
</script>

<template>
  <div class="projectsDiv">
    <Transition>
      <div v-if="rendered">
        <TransitionGroup name="projectList" tag="div">
        </TransitionGroup>
      </div>
    </Transition>
  </div>
</template>

<style>
.projectsDiv {
  width: 900px;
  height: 900px;
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