<script setup>
    const personagem = defineProps(["name", "url", "image", "status", "species", "gender", "location", "episode"])
</script>

<template>
    <div class="col-md-4">
        <div class="card mb-3 p-2">
            <!-- <p class="text-center">{{ personagem.name }}</p> -->
            <img :src="personagem.image" class="card-img-top" height="100%" alt="...">
            <div class="card-body">
                <p class="card-title">Nome: {{ personagem.name }}</p>
                <p class="card-title">Status: {{ personagem.status }}</p>
                <p class="card-title">Espécie: {{ personagem.species }}</p>
                <p class="card-title">Gênero: {{ personagem.gender }}</p>
                <p class="card-title">Localização: {{ personagem.location.name }}</p>
                <p class="card-title">Episódios: {{ personagem.episode.length }}</p>
                <!-- <p class="card-text">{{ personagem.url }}</p> -->
            </div>
        </div>
    </div>
</template>

<style>

</style>