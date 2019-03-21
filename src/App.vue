<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <router-link to="/siswa">Data Siswa</router-link>
    <router-link to="/kelas">Data Kelas</router-link>
    <router-view/> --> <!-- update data yg di klik -->
    <h1>{{ nama }}</h1>
    <h2>Nama: <input v-model="nama"><br></h2>
    <h2>Nilai Anda:&nbsp{{ nilai }}</h2>
    <button @click="totalnilai">Kirim </button>  
    <h2>1. Pelajaran apa yang sulit dipahami ?</h2>
    <input type="radio" v-model="soal1" value="Bahasa Inggris">Bahasa Inggris &nbsp&nbsp
    <input type="radio" v-model="soal1" value="Bahasa Indonesia">Bahasa Indonesia &nbsp&nbsp
    <input type="radio" v-model="soal1" value="Matematika">Matematika &nbsp&nbsp
    <input type="radio" v-model="soal1" value="IPA">IPA &nbsp&nbsp<br>
    <h2>2. Hewan apa yang haram untuk dikonsumsi ?</h2>
    <input type="radio" v-model="soal2" value="Bebek">Bebek &nbsp&nbsp
    <input type="radio" v-model="soal2" value="Ayam">Ayam &nbsp&nbsp
    <input type="radio" v-model="soal2" value="Sapi">Sapi &nbsp&nbsp
    <input type="radio" v-model="soal2" value="Babi">Babi &nbsp&nbsp<br>
    <h2>3. Jurusan apa yang tidak ada di SMKN 4 Bandung?</h2>
    <input type="radio" v-model="soal3" value="AVI">AVI &nbsp&nbsp
    <input type="radio" v-model="soal3" value="RPL">RPL &nbsp&nbsp
    <input type="radio" v-model="soal3" value="TSM">TSM &nbsp&nbsp
    <input type="radio" v-model="soal3" value="TKJ">TKJ &nbsp&nbsp<br>
  </div>
</template>

<script>
/*import HelloWorld from './components/HelloWorld.vue'*/

export default {
  name: 'app',
  data() {
    return{
      nama: '',
      nilai: 0,
      soal1: '',
      soal2: '',
      soal3: ''
      /*components: {
        HelloWorld
      }*/
    }
  },
methods: {
  totalnilai(){
    if (this.soal1 == 'Matematika' && this.soal2 == 'Babi' && this.soal3 == 'TSM') {
      this.nilai=+3    
    }
    else if (this.soal1 == 'Matematika' && this.soal2 == 'Babi') {
      this.nilai=+2 
    }
    else if (this.soal1 == 'Matematika' && this.soal3 == 'TSM') {
      this.nilai=+2 
    }
    else if (this.soal2 == 'Babi' && this.soal3 == 'TSM') {
      this.nilai=+2 
    }
    else if (this.soal1 == 'Matematika') {
      this.nilai=+1 
    }
    else if (this.soal2 == 'Babi') {
      this.nilai=+1 
    }
    else if (this.soal3 == 'TSM') {
      this.nilai=+1 
    }
    else {
      this.nilai = 0 
    }
  }
}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
