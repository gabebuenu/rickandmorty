<script setup>
    const personagem = defineProps(["name", "url", "image", "status", "species", "gender", "location", "episode"])

    let statusMap = {
    "Alive": {
        status: "Vivo",
        circle: "green",
        statusColor: "green"
    },
    "Dead": {
        status: "Morto",
        circle: "darkred",
        statusColor: "darkred"
    },
    "unknown": {
        status: "Desconhecido",
        circle: "gray",
        statusColor: "gray"
    },
    "default": {
        statusColor: "black"
    }
};

let personagemStatus = personagem.status;
let statusObj = statusMap[personagemStatus] || statusMap.default;

let status = statusObj.status || personagemStatus;
let circle = statusObj.circle || "black";
let statusColor = statusObj.statusColor || "black";


</script>

<template>
    <div class="col-md-4">
        <div class="card mb-3 p-2">
            <!-- <p class="text-center">{{ personagem.name }}</p> -->
            <img :src="personagem.image" class="card-img-top" height="100%" alt="...">
            <div class="card-body">
                <p class="card-title">Nome: {{ personagem.name }}</p>
                <p class="text-center">Status: <strong :style="{color: statusColor}">{{ status }}</strong><i class="bi bi-circle-fill" :style="{color:circle}"></i></p>
                <p class="card-title">Espécie: {{ personagem.species }}</p>
                <p class="card-title">Gênero: {{ personagem.gender }}</p>
                <p class="card-title">Localização: {{ personagem.location.name }}</p>
                <p class="card-title">Episódios Aparecidos: {{ personagem.episode.length }}</p>
                <!-- <p class="card-text">{{ personagem.url }}</p> -->
            </div>
        </div>
    </div>
</template>

<style>

</style>
