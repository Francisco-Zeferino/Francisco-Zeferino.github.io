<script setup>
import {ref} from 'vue';
const dataProps = defineProps({
  rendered : Boolean
})
</script>

<template>
  <div class="projectsDiv">
    <Transition>  
      <h2 v-if="rendered">Projects</h2>
    </Transition>
  </div>
</template>

<style>
.v-enter-active,
.v-leave-active {
  transition: opacity 1s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>