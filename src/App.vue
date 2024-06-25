<template>
  <div id="app">
    <!-- 1. Elemen HTML yang berbeda -->
    <h1>{{ greeting }}</h1>
    <p>Selamat datang di aplikasi Vue.js sederhana!</p>
    
    <!-- 2. Input teks -->
    <input type="text" v-model="inputText" placeholder="Masukkan teks...">
    
    <!-- 3. Class bindings dan style bindings -->
    <div :class="{ 'highlight': isHighlighted }" :style="{ 'font-weight': isBold ? 'bold' : 'normal' }">
      {{ dynamicStyleText }}
    </div>
    
    <!-- 4. Interaksi dinamis dengan event listeners -->
    <button @click="toggleStyle">Toggle Style</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      greeting: 'Halo!',
      inputText: '',
      isHighlighted: false,
      isBold: false
    };
  },
  computed: {
    dynamicStyleText() {
      return this.inputText.toUpperCase();
    }
  },
  methods: {
    toggleStyle() {
      this.isHighlighted = !this.isHighlighted;
      this.isBold = !this.isBold;
    }
  }
};
</script>

<style>
.highlight {
  background-color: yellow;
}
</style>
