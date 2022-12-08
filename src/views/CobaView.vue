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
            'vue 3'
          ]
        },
        styleObject: {
          color: 'green',
          fontSize: '50px'
        },
        isActive: false,
        error: null,
        awesome: true
      }
    },

    computed: {
      publishedBooks() {
        return this.author.books.length > 0 ? 'YES' : 'NO'
      },
      jikaYa() {
        return this.author.books.length
      },
      classObject() {
        return {
          active: this.isActive && !this.error,
          'text-danger': this.error && this.error.type === 'Fatal'
        }
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
      },
      changeAwesome() {
        this.awesome = !this.awesome
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
        <button @click="decrement">Kurangi dari keranjang</button>
        <div class="flex">
            <h2>Apakah {{ author.name }} memiliki buku ?</h2>
            <span>{{ publishedBooks }} | Jumlah buku {{ author.name }} ada {{ jikaYa }} buah</span>
        </div>

        <h2 :style="styleObject">Style Binding</h2>
        <h2 :class="classObject">Class Binding</h2>

        <button @click="changeAwesome()">CKick This</button>
        <h1 v-if="awesome">Vue is awesome</h1>
        <h1 v-else>Oh noooo!!</h1>

    </div>
</template>