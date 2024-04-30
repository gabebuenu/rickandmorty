<script setup>
import {ref} from 'vue'
</script>

<template>
  <nav class="navbar">
  <div class="container-fluid">
    <!-- <a class="navbar-brand" href="#">Rick and Morty</a> -->
    <img src="https://i.pinimg.com/564x/da/0b/5a/da0b5abb94cb1a3a242e98e6ec1aae83.jpg" height="60" alt="Logo" class="navbar-logo" style="transform: scaleX(-1);">
    <router-link class="navbar-brand" to="/">Rick and Morty</router-link>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <!-- <a class="nav-link active" aria-current="page" href="#">Início</a> -->
          <router-link class="nav-link" aria-current="page" to="/">Inicio</router-link>
        </li>
        <li class="nav-item">
          <!-- <a class="nav-link" href="#">Sobre</a> -->
          <router-link class="nav-link" to="/about">Sobre</router-link>
        </li>
      </ul>
    </div>
  </div>
</nav>

<div class="main">
  <router-view></router-view>
</div>

<footer class="footer text-light">
  <div class="a">
    &copy; Gabriel Bueno da Silva {{ new Date().getFullYear() }}
  </div>
</footer>
</template>
<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap');
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}

.section{
  width: 100%;
  justify-content: center;
  position: relative;
}

.template{
  align-items: center;
}


.navbar-logo{
  float: right;
}

.carde {
    border: none;
    float: left;
    text-align: center;
}
.cardi{
  width: 200%;
  text-align: center;
  align-items: center;
  border: none;
  float: left;
}

.card {
    border: none;
    float: left;
    text-align: center
}

.card-text {
    background-image: url('https://raw.githubusercontent.com/gabebuenu/guardarimagens/main/personagens.png');
    background-size: 550px 60px; 
    align-items: center;
    background-repeat: no-repeat; 
    color: transparent;
    text-align: center; 
}


.navbar-brand{
  color: #FFFFFF;
}
.nav-link{
  color: #FFFFFF;
  text-align: center;
  align-items: center;
}
.navbar{
  background-color: #000000;
  align-items: center;
  border-radius: 2px;
}

.texto {
  position: absolute;
  top: 250px;
  right: 20px; 
  width: 600px; 
  text-align: right; 
}

.texto h1{
  font-size: 20px;
}


footer{
  position: relative;
  bottom: 0;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 50px;
  background-color: #000000;
}

.footer{
  background-color: #000000;
}

.figure{
  align-items: center;
  justify-content: center;
  float: left;
  object-fit: cover;
  display: flex;
  position: relative;
  top: 10px;
}

.editar{
  width: 100%;
  justify-content: center;
  position: relative;
}

.figure-caption {
  top: 250px;
  right: 20px; 
  width: 100%; 
  font-size: 150%;
  padding: 10px 30px 10px 100px;
}

.pagination {
  display: flex;
  float: right;
  list-style: none;
  padding: 0;
}

.page-item {
  margin: 0 5px;
}

.page-link {
  color: #000000;
  text-decoration: none;
}

.page-link:hover {
  text-decoration: none;
}

.page-link:focus {
  box-shadow: none;
}

.page-link span {
  display: inline-block;
  width: 1em;
  height: 1em;
  vertical-align: -0.125em;
}

.page-link:focus span {
  box-shadow: 0 0 0 0.2rem rgba(37, 37, 37, 0.25);
}

.page-link:hover span {
  color: #1f1f1f;
}

.page-link[aria-disabled="true"] {
  color: #6c757d;
  pointer-events: none;
  cursor: not-allowed;
}

.page-item.active .page-link {
  z-index: 1;
  color: #fff;
  background-color: #161616;
  border-color: #2e2e2e;
}

.page-item.disabled .page-link {
  color: #6c757d;
  pointer-events: none;
  background-color: transparent;
  border-color: #dee2e6;
}

@media screen and (max-width: 768px) {
    .section {
        width: 90%;
    }
    .template{
        width: 90%;
    }
    .pagination{
      justify-content: center;
      align-items: center;
    }
}

@media screen and (max-width: 480px) {
    .section {
        width: 100%;
    }
    .template{
        width: 100%;
    }
}
</style>

