<script setup>
import { Transition, ref } from 'vue';
import ProjectsBar from './ProjectsBar.vue';
import ProjectsCard from './ProjectsCards.vue'

const welcomeText = ref('Welcome to my Portfolio!');
const roleText = ref('My name is Francisco and I am a Software Engineer student at 42 Lisboa');
const i = ref(0);

const welcomeTextFinished = ref(false);
const roleTextFinished = ref(false);
var arrowDownShow = ref(false);

window.onload = function() {
  writeText();
  document.body.style.overflow = 'hidden';
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
        arrowDownShow.value = true;
        document.body.style.overflow = '';
      }, 1000);
    }
  }
}
</script>

<template>
    <div class="welcomeDiv">
      <div class="about-me">
        <h1 id="welcomeText"></h1>
        <h2 id="roleText"></h2>
        <Transition>
          <div v-if="arrowDownShow">
            <img src="../assets/arrow-down.png" alt="arrow-down" width="25px" height="25px" class="arrow-down"/>
          </div>
        </Transition>
        <!--<ProjectsBar :rendered="roleTextFinished"/>-->
        <ProjectsCard v-if="roleTextFinished"/>
      </div>
    </div> 
</template>

<style>
html {
  scrollbar-width: none;
  -ms-overflow-style: none;
}

.v-enter-active,
.v-leave-active {
  transition: opacity 1s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

.arrow-down{
  align-items: center;
  margin-left: 350px;
  margin-right: 350px;
  margin-top : 40px;
  margin-bottom : 50px;
  opacity: 0.5;
}

.about-me{
      width: 750px;
      height: 100px;
      position: absolute;
}

#welcomeText{
  font-size: 50px;
  font-weight: bold;
}

.welcomeDiv{
  display:flex;
  justify-content: center;
  align-items:flex-start;
  width: 100%;
  height: 300px;
}
</style>