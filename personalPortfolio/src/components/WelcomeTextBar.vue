<script setup>
import { ref, render } from 'vue';
import ProjectsBar from './ProjectsBar.vue';
const welcomeText = ref('Welcome to my Portfolio!');
const roleText = ref('I am a Sotware Engineer student at 42 Lisboa');
const i = ref(0);
const welcomeTextFinished = ref(false);
const roleTextFinished = ref(false);
window.onload = function() {
  writeText();
}

function writeText() {
  if(i.value < welcomeText.value.length) {
    document.getElementById('welcomeText').innerHTML += welcomeText.value.charAt(i.value);
    i.value++;
    setTimeout(writeText, 75);
  }
  else {
    welcomeTextFinished.value = true;
  }
  if(welcomeTextFinished.value === true) {
    i.value = 0;
    writeRoleText();
  }

  function writeRoleText() {
  if(i.value < roleText.value.length) {
    document.getElementById('roleText').innerHTML += roleText.value.charAt(i.value);
    i.value++;
    setTimeout(writeRoleText, 25);
  }
  else {
      setTimeout(() => {
        roleTextFinished.value = true;
      }, 1000);
    }
  }
}
</script>

<template>
  <div class="container">
    <div class="welcomeDiv">
      <h1 id="welcomeText"></h1>
      <h2 id="roleText"></h2>
    </div>
    <ProjectsBar :rendered="roleTextFinished" />
  </div> 
</template>

<style>
.container{
  display: flex;
  column-gap: 40px;
}

.welcomeDiv{
  height: 500px;
  width: 500px;
}
</style>