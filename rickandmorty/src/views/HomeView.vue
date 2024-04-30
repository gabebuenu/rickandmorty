<script setup>
// props - onMounted, reactive, ref
import { onMounted, reactive, ref } from 'vue';
import ListPersonagens from '../components/ListPersonagens.vue';

// Inspiração da pagination, atráves de um colega

let personagens = reactive(ref());
let pagina = 1

onMounted(() => {
  trocarPersonagens();
});

function trocarPersonagens() {
  fetch("https://rickandmortyapi.com/api/character?page=" + pagina)
    .then(response => response.json())
    .then(response => {
      personagens.value = response.results;
      console.log(personagens);

    });
}

function Proxima() {
  pagina++;
  trocarPersonagens();
  personagens.value = []
}

function Voltar() {
  if (pagina > 1) {
    pagina--;
    trocarPersonagens();
    personagens.value = []
  }
}
</script>


<template>
<body>
  <section>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-6">
          <div class="carde" style="width: 35rem" text-align: center>
            <img src="https://i.pinimg.com/736x/ea/b1/20/eab1207da589ec7d1a17696fa5e7ba32.jpg" class="card-img-top" alt="..." style="border-radius: 10px; text-align: center; width: 100%; object-fit: cover;">
            <h1 class="card-text">Personagens de Rick and Morty</h1>
          </div>
        </div>
        <div class="texto">
        <h1>Rick & Morty: Este programa ensina a respeitar o idoso, mesmo que seja um alcoólatra perigoso, que vive em uma realidade paralela e que é seu próprio avô.</h1>
      </div>  
        <section>        
        <div class="col-sm-12 col-md-6">
          <div class="cardi">
            <div class="card-body row">
              <ListPersonagens 
            v-for="personagem in personagens"
            :key="personagem.name"
            :name="personagem.name"
            :url="personagem.url"
            :image="personagem.image"
            :status="personagem.status"
            :species="personagem.species"
            :gender="personagem.gender"
            :location="personagem.location"
            :episode="personagem.episode" />
            </div>
            <nav aria-label="Page navigation example">
              <ul class="pagination">
                <li class="page-item">
                  <a class="page-link" href="#" aria-label="Previous" @click="Voltar()">
                    <span aria-hidden="true">&laquo;</span>
                  </a>
                </li>
                <li class="page-item"><a class="page-link" href="#">{{ pagina }}</a></li>
                <li class="page-item">
                  <a class="page-link" href="#" aria-label="Next" @click="Proxima()">
                <span aria-hidden="true">&raquo;</span>
                  </a>
                </li>
              </ul>
            </nav>
          </div>
        </div>
      </section>
      </div>
    </div>
  </main>
</section>
</body>
</template>

