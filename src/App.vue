<script setup lang="ts">
import { ref } from 'vue'

const modalHandler = ref(false)
</script>

<template>
  <main>
    <Modal />
    <div v-if="modalHandler" class="overlay">
      <div class="modal">
        <button @click="modalHandler = false" class="close">X</button>
        <textarea name="" id="" cols="30" rows="10"></textarea>
        <button>Add note</button>
      </div>
    </div>
    <div class="container">
      <header>
        <h1>Notes {{ modalHandler }}</h1>
        <button @click="modalHandler = true">+</button>
      </header>
      <div class="cards__container">
        <div class="card">
          <p class="main__text">
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Nesciunt tempore id eos est,
            non iusto!
          </p>
          <p class="date">1-1-2020</p>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.container {
  max-width: 1000px;
  padding: 10px;
  margin: 0 auto;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h1 {
  font-weight: bold;
  margin-bottom: 3rem;
  font-size: 2.5rem;
}

button {
  border: none;
  padding: 1rem;
  height: 50px;
  width: 50px;
  cursor: pointer;
  color: grey;
  border-radius: 50%;
  color: wheat;
  font-size: 1.5rem;
  background-color: grey;
  display: flex;
  justify-content: center;
  align-items: center;
}

.card__container {
  display: flex;
  flex-wrap: wrap;
}

.card {
  width: 12.5rem;
  height: 12.5rem;
  background-color: grey;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  border-radius: 1rem;
  color: white;
}

.overlay {
  position: absolute;
  width: 80%;
  height: 50%;
  background-color: transparent;
  z-index: 10;
  display: flex;
  align-items: center;
  justify-content: center;
  /* display: none; */
}

.modal {
  width: 450px;
  background-color: grey;
  border-radius: 1rem;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  position: relative;
  gap: 2rem;
}

.modal button {
  background-color: black;
  font-size: 1rem;
  font-weight: bold;
}
</style>
