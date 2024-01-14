<script setup lang="ts">

function goGitHub() {
  window.open('https://github.com/EwertonHecsley', '_blank');
}

function goLinkedin() {
  window.open('https://www.linkedin.com/in/ewerton-hecsley-8a613992/', '_blank');
}

</script>

<template>
  <main>
    <div class="container-logo">
      <img src="../assets//images/logo_portal.jpg" alt="logo">
    </div>
    <div class="container-main">
      <div class="container-git-hub">
        <img src="../assets/images/GitHub-Logo.svg" alt="">
        <button @click="goGitHub" type="button">Git Hub</button>
      </div>
      <div>
        <h1 style="color:rgba(0, 255, 0, 0.5); font-size: 60px;font-family: 'Rubik Burned', system-ui;">
          Consumindo a API
        </h1>
      </div>
      <div class="container-linkedin">
        <img src="../assets/images/linkedin.svg" alt="">
        <button @click="goLinkedin" type="button">Linkedin</button>
      </div>
    </div>
  </main>
</template>
<style>
html,
body {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  height: 100%;
  margin: 0;
  padding: 0;
  background-color: black;
}

main {
  display: flex;
  flex-direction: column;
  align-items: center;
}

main img {
  height: 450px;
}

.container-main {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 70vw;
  margin: 0px 200px;
}

.container-git-hub {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
  border-style: none;
  height: 30vh;
  width: 15vw;
  background-color: rgb(28, 39, 24);
  border-radius: 10px;
  box-shadow: 5px 5px 10px rgba(0, 255, 0, 0.5);
  overflow: hidden;
}

.container-git-hub button:hover {
  background-color: green;
  box-shadow: 5px 5px 10px rgba(1, 26, 1, 0.5);
  color: wheat;
}

.container-git-hub img {
  height: 120px;
}

.container-git-hub button {
  width: 70%;
  height: 50px;
  border-radius: 10px;
  border-style: none;
  background-color: rgb(10, 255, 0, 0.5);
  font-size: larger;
}

.container-linkedin {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
  border-style: none;
  height: 30vh;
  width: 15vw;
  background-color: rgb(28, 39, 24);
  border-radius: 10px;
  box-shadow: 5px 5px 10px rgba(0, 255, 0, 0.5);
  overflow: hidden;
}

.container-linkedin button:hover {
  background-color: green;
  box-shadow: 5px 5px 10px rgba(1, 26, 1, 0.5);
  color: wheat;
}

.container-linkedin img {
  height: 120px;
}

.container-linkedin button {
  width: 70%;
  height: 50px;
  border-radius: 10px;
  border-style: none;
  background-color: rgb(10, 255, 0, 0.5);
  font-size: large;
}
</style>
