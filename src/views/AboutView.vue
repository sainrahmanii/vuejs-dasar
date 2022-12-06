<script>
  export default {
    data() {
      return {
        keranjang : 0
      }
    },
    methods: {

      increment() {
        this.keranjang++
      },
      decrement() {
        this.keranjang--
      },
      reset() {
        this.keranjang = 0
      }
    },
    mounted() {
      this.increment,
      this.decrement,
      this.reset
    }
  }
</script>

<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h2>Barang di keranjang ada {{ keranjang }}</h2>
    <button @click="increment">Tambah Ke keranjang</button>
    <button @click="decrement">Kurangi Ke keranjang</button>
    <button @click="resest">Reset</button>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
