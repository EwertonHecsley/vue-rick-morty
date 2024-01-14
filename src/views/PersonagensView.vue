<script setup lang="ts">
import { onBeforeMount, ref } from 'vue';
import axios from '../axios';
import PersonagemCard from '../components/PersonagemCard.vue';

interface Info {
    count: number;
    pages: number;
    next: string;
    prev: string | boolean;
}

interface Personagem {
    id: number;
    name: string;
    image: string;
    gender: string;
    species: string;
    status: string;
}

const listOfPerson = ref<Personagem[]>([]);
const information = ref<Info | null>(null);

const carregarPersonagens = async (url: string) => {
    try {
        const response = await axios.get(url);
        listOfPerson.value = response.data.results;
        information.value = response.data.info;
    } catch (error) {
        console.error('Erro ao consultar personagens', error);
    }
};

const carregarProximaPagina = () => {
    if (information.value?.next) {
        carregarPersonagens(information.value.next);
    }
};

const carregarPaginaAnterior = () => {
    if (typeof information.value?.prev === 'string') {
        carregarPersonagens(information.value.prev);
    }
};

onBeforeMount(() => {
    carregarPersonagens('/character');
});
</script>

<template>
    <div class="container">
        <div>
            <h1>Lista de Personagens</h1>
        </div>
        <div class="container-btn">
            <button @click="carregarPaginaAnterior" v-if="information?.prev !== null">Voltar
                Página</button>
            <button @click="carregarProximaPagina">Próxima Página</button>
        </div>
        <div class="container-card">
            <PersonagemCard v-for="personagem in listOfPerson" :key="personagem.id" :personagem="personagem" />
        </div>
        <div class="container-btn">
            <button @click="carregarPaginaAnterior" v-if="information?.prev !== null">Voltar Página</button>
            <button @click="carregarProximaPagina">Próxima Página</button>
        </div>
    </div>
</template>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    color: wheat;
}

.container-card {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}

.container-btn {
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    width: 20%;
    margin: 5px;
}

.container-btn button {
    border-radius: 10px;
    border-style: none;
    background-color: rgb(10, 255, 0, 0.5);
    font-size: larger;
    padding: 10px;
}

.container-btn button:hover {
    background-color: green;
    box-shadow: 5px 5px 10px rgba(1, 26, 1, 0.5);
    color: wheat;
}
</style>
