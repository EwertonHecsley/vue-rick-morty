<script setup lang="ts">

</script>

<template>
  <main>
    <div class="container-logo">
      <img src="../assets//images/logo_portal.jpg" alt="logo">
    </div>
    <div class="container-main">
      <div class="container-git-hub">
        <img src="../assets/images/GitHub-Logo.svg" alt="">
        <button type="button">Git Hub</button>
      </div>
      <div>
        <h1 style="color: wheat;">Conteudo de texto</h1>
      </div>
      <div>
        <img src="" alt="">
        <button type="button">Linkedin</button>
      </div>
    </div>
  </main>
</template>
<style>
html,
body {
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
  height: 550px;
}

.container-main {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 70vw;
  margin: 10px 200px;
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

.container-git-hub img {
  height: 120px;
}

.container-git-hub button {
  width: 70%;
  height: 50px;
  border-radius: 10px;
  border-style: none;
  background-color: rgb(10, 255, 0, 0.5);
}
</style>
