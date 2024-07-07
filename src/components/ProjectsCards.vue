<script>
import {ref} from 'vue';
</script>

<template>
    <div class="projectsSection">
        <div class="card">
            <div class="container">
                <h3>Ola</h3>
                <p>Description</p>
            </div>
        </div>
        <div class="card">
            <div class="container">
                <h3>Ola</h3>
                <p>Description</p>
            </div>
        </div>
        <div class="card">
            <div class="container">
                <h3>Ola</h3>
                <p>Description</p>
            </div>
        </div>
        <div class="card">
            <div class="container">
                <h3>Ola</h3>
                <p>Description</p>
            </div>
        </div>
        <div class="card">
            <div class="container">
                <h3>Ola</h3>
                <p>Description</p>
            </div>
        </div>
        <div class="card">
            <div class="container">
                <h3>Ola</h3>
                <p>Description</p>
            </div>
        </div>
        <div class="card">
            <div class="container">
                <h3>Ola</h3>
                <p>Description</p>
            </div>
        </div>
        <div class="card">
            <div class="container">
                <h3>Ola</h3>
                <p>Description</p>
            </div>
        </div>
    </div>
</template>

<style>
.projectsSection{
    margin-top: 700px ;
    display: flex;
    align-content: space-around;
    flex-wrap: wrap;
    justify-content: center; /* Center horizontally */
    align-items: center; /* Center vertically */
    height: 500px; /* Full viewport height */
}

.card {
    display: flex;
    background-color: white;
    text-align: left;
    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    transition: 0.3s;
    border-radius: 5px;
    margin-right: 25px;
    margin-top: 25px;    
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.container {
  width: 200px;
  color: black;
  padding: 2px 16px;
}
</style>