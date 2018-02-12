<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld/>
    <button @click="open">打开</button>
    <myDialog :isShow="isShow" @onClose="closeDialog"></myDialog>

    
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Dialog from './components/dialog.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    myDialog : Dialog
  },
  data(){
    return {
      isShow : false
    }
  },
  methods: {
    open(){
      this.isShow = true;
    },
    closeDialog(){
      this.isShow = false;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
