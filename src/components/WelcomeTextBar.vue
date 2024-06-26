<script setup>
import { Transition, ref } from 'vue';
import {useScrollLock } from '@vueuse/core';
import ProjectsBar from './ProjectsBar.vue';

const welcomeText = ref('Welcome to my Portfolio!');
const roleText = ref('My name is Francisco and I am a Software Engineer student at 42 Lisboa');
const i = ref(0);

const welcomeTextFinished = ref(false);
const roleTextFinished = ref(false);
var arrowDownShow = ref(false);

window.onload = function() {
  document.body.style.overflow = 'hidden';
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
        document.body.style.overflow = '';
        arrowDownShow.value = true;
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
        <ProjectsBar :rendered="roleTextFinished"/>
      </div>
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

.arrow-down{
  align-items: center;
  margin-left: 350px;
  margin-right: 350px;
  margin-top : 50px;
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