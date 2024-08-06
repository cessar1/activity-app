<script setup>
import { ref } from 'vue'
const { isOpen } = defineProps({
  isOpen: Boolean
})
const emit = defineEmits(['close', 'submit'])

const name = ref('')
const description = ref('')
const category = ref('')

const closeModal = () => {
  emit('close')
}
const submitForm = () => {
  emit('submit', {
    name: name.value,
    description: description.value,
    category: category.value
  })
  closeModal()
}
</script>

<template>
  <div v-if="isOpen" class="modal-overlay">
    <div class="modal">
      <h2>Nueva Actividad</h2>
      <div class="divider"></div>
      <form @submit.prevent="submitForm">
        <div class="form-group">
          <label for="name">Nombre</label>
          <input v-model="name" id="name" required />
        </div>
        <div class="form-group">
          <label for="description">Descripción:</label>
          <textarea v-model="description" id="description" required></textarea>
        </div>
        <div class="form-group">
          <label for="category">Categoría</label>
          <select v-model="category" id="category" required>
            <option value="">Selecciona una categoría</option>
            <option value="trabajo">Trabajo</option>
            <option value="personal">Personal</option>
            <option value="estudio">Estudio</option>
          </select>
        </div>
        <div class="form-action">
          <button type="submit">Guardar</button>
          <button type="button" @click="closeModal">Cancelar</button>
        </div>
      </form>
    </div>
  </div>
</template>

<style scoped>
.modal-overlay {
  display: flex;
  place-items: center;
  justify-content: center;
  position: fixed;
  width: 100%;
  height: 100vh;
  background-color: rgb(1, 1, 1, 0.6);
}
h2 {
  padding: 10px 0;
  font-weight: 700;
  font-style: italic;
}
.divider {
  border-bottom: 1px solid #9e9779;
}

.modal {
  background-color: #dec584;
  border: 3px solid #9e9779;
  padding: 20px;
  border-radius: 8px;
  width: 80%;
  max-width: 500px;
}
.form-group {
  /* display: flex;
  justify-content: space-between;
  gap: 32px;
  border: 1px solid blue; */
}
.form-action {
  display: flex;
  justify-content: flex-end;
  gap: 10px;
}

button {
  padding: 8px 16px;
  margin-top: 15px;
  border-radius: 4px;
  cursor: pointer;
  border: 3px solid #9e9779;
  color: #ffff;
}

button[type='submit'] {
  background-color: #709f9d;
}

button[type='button'] {
  background-color: #a16b56;
}

label {
  display: block;
  font-weight: 700;
  margin-top: 5px;
  font-style: italic;
}

input,
textarea,
select {
  width: 100%;
  padding: 8px;
  border-radius: 4px;
  max-width: 500px;
  border: 3px solid #9e9779;
}

input:focus,
textarea:focus,
select:focus {
  outline: none;
  border-color: #709f9d;
}
</style>
