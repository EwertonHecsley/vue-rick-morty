<script setup lang="ts">
import { onBeforeMount, ref } from 'vue';
import axios from '../axios';

interface Info {
    count: number
    pages: number
    next: string
    prev: string | boolean
}

interface Personagem {
    id: number
    name: string
    image: string
    gender: string
    species: string
    status: string
};

interface ResponseAPI {
    info: Info
    results: Personagem[]
}

const listOfPerson = ref<ResponseAPI[]>([]);

const getPersons = async () => {
    try {
        const response = await axios.get('/character');
        listOfPerson.value = response.data;
        console.log(listOfPerson);
    } catch (error) {
        console.error('Erro ao consultar personagens', error);
    }
};

onBeforeMount(getPersons);

</script>

<template>
    <main>
        <div class="container-cabeca">
            <h1 style="color:white">Lista de Personagens</h1>
        </div>
    </main>
</template>

<style scoped></style>