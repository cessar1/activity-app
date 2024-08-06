<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import ActivityModal from './components/ActivityModal.vue'

const isModalOpen = ref(false)

const openModal = () => {
  isModalOpen.value = true
}

const closeModal = () => {
  isModalOpen.value = false
}

const handleSubmit = (newActivity) => {
  // Aquí puedes manejar la lógica para guardar la nueva actividad
  closeModal()
}
function handleAddActivity() {
  openModal()
}
</script>

<template>
  <div class="activity-screen">
    <header>
      <h1>Actividades</h1>
    </header>
    <main class="content">
      <!-- Aquí irá el contenido principal -->
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <div>Cuando se grande</div>
      <div>Quiero ser como vos</div>
      <button class="add-button" @click="handleAddActivity">+</button>
    </main>
    <ActivityModal :isOpen="isModalOpen" @close="closeModal" @submit="handleSubmit" />
    <footer>
      <ul>
        <li>Actividades</li>
        <li>Graficos</li>
        <li>Configuraciones</li>
      </ul>
    </footer>
  </div>

  <RouterView />
</template>

<style scoped>
.content {
  border: 1px solid red;
  height: calc(100vh - 60px);
  overflow: scroll;
}
footer {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  background-color: var(--color-deep-taupe);
  color: var(--color-text-light);
  height: 60px;
  box-sizing: border-box;
}

footer ul {
  display: flex;
  decoration: none;
}
.activity-screen {
  height: 100vh;
  display: flex;
  flex-direction: column;
}

header {
  max-height: 100vh;
  padding: 1rem;
  background-color: var(--color-steel-blue);
  color: var(--color-text-light);
  text-align: center;
}

.add-button {
  position: absolute;
  bottom: 65px;
  right: 20px;
  border-radius: 50%;
  width: 60px;
  height: 60px;
  background-color: #7a9c66;
  /* border: 1px solid white; */
  border: 2px solid black;
  transition: box-shadow 0.3s ease;
}
.add-button:hover {
  box-shadow: 0 0 40px var(--color-green, #b5d299);
}
</style>
