<script setup>

  import { computed, reactive, ref } from 'vue';
  const nama = ref({ name: 'Husain Rahmani' })
  const keranjang = reactive({ count: 0 })
  const author = reactive({
    nama: 'Husain Rahmani',
    books: [
      'Fiqih Muamalah',
      'Aqidah',
      'Hadits Arbain'
    ]
  })

  const publishedBooksMessage = computed(() => {
      return author.books.length > 0 ? 'Yes' : 'No'
  })

  function increment() {
    keranjang.count++
  }

  function decrement() {
    keranjang.count--
  }

</script>

<template>
  <main>
    <h2>{{ nama.name }}</h2>
    <h1>My Belanjaan {{ keranjang.count }}</h1>
    <button @click="increment">
      Tambah Belanjaan
    </button>
    <button @click="decrement">
      Kurangi Belanjaan
    </button>
    <h2>{{ author.nama }} Punya Buku ?</h2>
    <span>{{ publishedBooksMessage }}</span>
    <h1>Jumlah Buku : {{ author.books.length }}</h1>
  </main>
</template>
