<script setup lang="ts">
import { ref, defineProps } from 'vue';

const handleImageLoaded = ref(false);

const handleImageLoad = () => {
    handleImageLoaded.value = true;
};

const props = defineProps(['personagem']);

</script>

<template>
    <div class="card">
        <img :src="props.personagem.image" :alt="props.personagem.name" @load="handleImageLoad" />
        <div class="info">
            <h2>{{ props.personagem.name }}</h2>
            <p>Status: {{ props.personagem.status }}</p>
            <p>Espécie: {{ props.personagem.species }}</p>
        </div>
    </div>
</template>

<style scoped>
.card {
    border: 1px solid #ccc;
    border-radius: 8px;
    overflow: hidden;
    margin: 10px;
    padding: 10px;
    width: 200px;
    text-align: center;
}

img {
    width: 100%;
    height: auto;
    border-radius: 4px;
}

.info {
    margin-top: 10px;
}

.card.loaded {
    visibility: visible;
}
</style>