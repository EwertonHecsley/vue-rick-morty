<script setup lang="ts">
import { RouterLink } from 'vue-router';
</script>
<template>
    <div class="container-cabeca">
        <ul>
            <RouterLink to="/">
                <li>Home</li>
            </RouterLink>
            <RouterLink to="/personagens">
                <li>Personagens</li>
            </RouterLink>
            <li>Episódios</li>
        </ul>
    </div>
</template>
<style scoped>
.container-cabeca ul {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 15vw;
    margin: auto;
    padding-top: 10px;
}

ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

li {
    color: wheat;
    display: inline-block;
    transition: color 0.5s ease, font-size 0.5s ease;
}

li:not(:last-child)::after {
    content: '|';
    margin-left: 15px;
    color: wheat;
}

li:hover {
    color: #006400;
    font-size: 1.1em;
    cursor: pointer;
}
</style>