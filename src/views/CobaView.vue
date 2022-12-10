<script>
  import ButtonVue from '@/components/Button.vue'

  export default {
    data() {
      return {
        msg: 'SUBMIT',
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
        awesome: true,
        buah: [
          "Mangga",
          "Anggur",
          "Apel",
          "Pir",
          "Melon",
          "Semangka"
        ],
        selected: 'A',
        options: [
          {text: 'One', value: 'A'},
          {text: 'Two', value: 'B'},
          {text: 'Three', value: 'C'},
          {text: 'Four', value: 'D'},
          {text: 'Five', value: 'E'},
          {text: 'Six', value: 'F'},
        ],
        message: '',
        checkNames: [],
      }
    },
    components: {
      ButtonVue
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
      },
      shortBuah() {
        return this.buah.sort()
      }
    },
    methods: {

      increment() {
        this.keranjang++
      },
      say(message){
        alert(message)
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
    <main>
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

        <button @click="changeAwesome()">Click This</button>
        <h1 v-if="awesome">Vue is awesome</h1>
        <h1 v-else>Oh noooo!!</h1>

        <!-- <h2 v-for="(item, index) in shortBuah">
          {{ index }} {{ item }}
        </h2> -->

        <button @click="say('Hi!')">Say Hi!</button>

        <select v-model="selected">
          <option v-for="option in options" :value="option.value">
            {{ option.text }}
          </option>
        </select>

        <p>Message is: {{ message }}</p>
        <textarea v-model="message" placeholder="Tuliskan disini"></textarea>

        <div>Checked names: {{ checkNames }}</div>

        <input type="checkbox" id="jack" value="Jack" v-model="checkNames">
        <label for="jack">Jack</label>

        <input type="checkbox" id="john" value="John" v-model="checkNames">
        <label for="john">John</label>

        <input type="checkbox" id="mike" value="Mike" v-model="checkNames">
        <label for="mike">Mike</label>
        <br>
        <button-vue >
          {{ author.name }}
        </button-vue>
    </div>
    </main>
</template>