<script>
import {ref} from 'vue';
</script>

<template>
    <div class="projectsSection">
        <div class="card">
            <div class="container">
                <h4>1</h4>
                <p>2</p>
            </div>
        </div>
        <div class="card">
            <div class="container">
                <h4>1</h4>
                <p>2</p>
            </div>
        </div>
        <div class="card">
            <div class="container">
                <h4>1</h4>
                <p>2</p>
            </div>
        </div>
        <div class="card">
            <div class="container">
                <h4>1</h4>
                <p>2</p>
            </div>
        </div>
        <div class="card">
            <div class="container">
                <h4>1</h4>
                <p>2</p>
            </div>
        </div>
        <div class="card">
            <div class="container">
                <h4>1</h4>
                <p>2</p>
            </div>
        </div>
    </div>
</template>

<style>
.projectsSection{
  display:flex;
  justify-content: center;
  align-items:flex-start;
  width: 100%;
  height: 300px;
}

.card {
    display: inline-block;
    background-color: white;
    text-align: left;
    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    transition: 0.3s;
    width: 350px;
    border-radius: 5px;
    margin-right: 25px;
    margin-top: 25px;    
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.container {
  color: black;
  padding: 2px 16px;
}
</style>