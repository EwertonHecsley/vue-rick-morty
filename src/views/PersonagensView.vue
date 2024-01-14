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

const carregarPersonagens = async () => {
    try {
        const response = await axios.get(information.value?.next || '/character');
        listOfPerson.value = response.data.results;
        information.value = response.data.info;
    } catch (error) {
        console.error('Erro ao consultar personagens', error);
    }
};

const carregarProximaPagina = (event: MouseEvent) => {
    event.preventDefault();
    carregarPersonagens();
};

onBeforeMount(() => {
    carregarPersonagens();
});
</script>

<template>
    <div class="container">
        <div>
            <h1>Lista de Personagens</h1>
        </div>
        <div class="container-card">
            <PersonagemCard v-for="personagem in listOfPerson" :key="personagem.id" :personagem="personagem" />
        </div>
        <div>
            <button v-if="information?.prev !== null" @click="carregarProximaPagina">Voltar Página</button>
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
</style>
