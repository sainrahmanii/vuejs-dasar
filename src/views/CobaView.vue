<script>
  export default {
    data() {
      return {
        keranjang : 0,
        author: {
          name: 'Husain Rahmani',
          books: [
            'vue',
            'vue 2',
            'vye 3'
          ]
        }
      }
    },

    computed: {
      publishedBooks() {
        return this.author.books.length > 0 ? 'YES' : 'NO'
      },
      jikaYa() {
        return this.author.books.length
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
    <div>
        <h1>This is an about page</h1>
        <h2>Barang di keranjang ada {{ keranjang }}</h2>
        <button @click="increment">Tambah Ke keranjang</button>
        <button @click="decrement">Kurangi Ke keranjang</button>
        <div class="flex">
            <h2>Apakah {{ author.name }} memiliki buku ?</h2>
            <span>{{ publishedBooks }} | Jumlah buku {{ author.name }} ada {{ author.books.length }} buah</span>
        </div> 
    </div>
</template>