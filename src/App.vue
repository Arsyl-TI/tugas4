<script setup>
import { ref } from 'vue';

const nama = ref('halo arsyl');
const message = ref('Halo dunia');
const clicked = ref(false);
const inputText = ref('');
const imageSrc = ref('https://vuejs.org/images/logo.png');
const handleClick = () => {
  clicked.value = true;
};
const showMessage = ref(true);
const toggleMessage = () => {
  showMessage.value = !showMessage.value;
}
</script>

<template>
<h1>{{ nama }}</h1>
<p>{{ message }}</p>

<input v-model="inputText" placeholder="Ketik sesuatu....">
<h3>Anda Mengetik : {{ inputText }}</h3>

<button @click="handleClick"> Klik saya!</button>
<p v-if="clicked">Tombol telah di klik</p>

<img :src="imageSrc" alt="Vue Logo" width="100">

<p v-if="showMessage">Tampilkan Pesan ini jika True</p>
<p v-else>Tampilkan pesan ini jika False</p>
<button @click="toggleMessage">Toggle pesan</button>
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
