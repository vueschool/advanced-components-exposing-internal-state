<script setup>
import { ref } from "vue"
import Modal from './components/jsx/Modal';

const modal = ref(null)
</script>

<template>
  <button @click="modal.open()">Outside trigger</button>
  <Modal ref="modal" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
