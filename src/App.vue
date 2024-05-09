<script setup lang="ts">
import { ref } from 'vue';
import Container from './components/global/Container.vue'

const title = ref('');
const selectedEmoji = ref('');
const selectedAppreciation = ref('');
const selectedTickets = ref([]);
const opinion = ref('');

</script>

<template>
  <Container>
    <div class="card">
      <div class="form-group">
        <label for="titulo">Titulo</label>
        <input id="titulo" v-model="title" type="text">
      </div>
      <hr>
      <div class="form-group">
        <label for="emoji">Emoji:</label>
        <select v-model="selectedEmoji" id="emoji">
          <option value="" disabled selected>Selecciona un emoji</option>
          <option value="😸">😸</option>
          <option value="😎">😎</option>
          <option value="🥳">🥳</option>
          <option value="🎉">🎉</option>
        </select>
      </div>
      <hr>
      <div class="form-group">
        <label>Apreciación:</label>
        <div class="radio-group">
          <div class="radio-option">
            <input type="radio" id="regular" name="apreciacion" value="Regular" v-model="selectedAppreciation">
            <label for="regular">Regular</label>
          </div>
          <div class="radio-option">
            <input type="radio" id="bien" name="apreciacion" value="Bien" v-model="selectedAppreciation">
            <label for="bien">Bien</label>
          </div>
          <div class="radio-option">
            <input type="radio" id="muybien" name="apreciacion" value="Muy bien" v-model="selectedAppreciation">
            <label for="muybien">Muy bien</label>
          </div>
          <div class="radio-option">
            <input type="radio" id="increible" name="apreciacion" value="Increible" v-model="selectedAppreciation">
            <label for="increible">Increíble</label>
          </div>
        </div>
      </div>
      <hr>
      <div class="form-group">
        <label>Apreciación:</label>
        <div class="ticket-group">
          <div class="ticket-pair">
            <input type="checkbox" id="metodologia" value="Metodología de un componente" v-model="selectedTickets">
            <label for="metodologia">Metodología de un componente</label><br>
          </div>
          <div class="ticket-pair">
            <input type="checkbox" id="directivas" value="Directivas" v-model="selectedTickets">
            <label for="directivas">Directivas</label><br>
          </div>
          <div class="ticket-pair">
            <input type="checkbox" id="one-way" value="One-Way y Two-way data binding" v-model="selectedTickets">
            <label for="one-way">One-Way y Two-way data binding</label><br>
          </div>
          <div class="ticket-pair">
            <input type="checkbox" id="estado" value="Estado" v-model="selectedTickets">
            <label for="estado">Estado</label><br>
          </div>
          <div class="ticket-pair">
            <input type="checkbox" id="mvvm" value="El patrón de diseño MVVM" v-model="selectedTickets">
            <label for="mvvm">El patrón de diseño MVVM</label><br>
          </div>
        </div>
      </div>
      <hr>
      <div class="form-group">
        <label for="opinion">Opinión</label>
        <textarea id="opinion" v-model="opinion" style="resize: none;"></textarea>
      </div>
    </div>
  </Container>
  <Container>
    <div class="card">
      <div class="text-center">
          {{ selectedEmoji }}
        <h1>Estoy aprendiendo Vue Js</h1>
        <h2>Y me parece {{ selectedAppreciation }}</h2>
        <p>He aprendido:</p>
        <ul class="ul-items">
          <li v-for="item in selectedTickets">{{ item }}</li>
        </ul>

        <p>Mi opinión hasta el ahora del framework es:</p>
        {{ opinion }}

      </div>
    </div>
  </Container>
</template>

<style scoped>
.card {
  background-color: white;
  padding: 20px;
  border-radius: 8px;
  margin-top: 50px;
}

.text-center {
  text-align: center;
}

.form-group {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}

.form-group label {
  margin-right: 10px;
}

.form-group textarea {
  flex: 1;
  background-color: #f5f5f5;
}

.radio-group {
  display: flex;
  align-items: center;
}

.radio-group input[type="radio"] {
  margin-right: 5px;
}

.ticket-group {
  display: flex;
  flex-wrap: wrap;
  column-count: 2;
}

.ticket-pair {
  flex-basis: calc(50% - 10px);
  padding: 5px;
}

.ul-items {
  width: 200px;
  margin: 0 auto;
}

</style>