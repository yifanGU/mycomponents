<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <html-2-word msg="Welcome to Your Vue.js App">
    <template  v-slot:content >我是内容</template>
    
    <template v-slot:button>
      <button  class='btn btn-primary'>
          {{ "hhh下载" }}
      </button>
    </template>
  </html-2-word>
  
</template>

<script>
import Html2Word from './components/Html2Word.vue'

export default {
  name: 'App',
  components: {
    Html2Word
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
