<template>
  <h1>{{ title }}</h1>
  <p>welcome...</p>
  <button @click="toggleModal">Click me</button>
  <!--<input type="text" ref="name">-->
  <!--<button @click="handleClick">Click me</button>-->
  <div v-if="showModal" >
    <modal :header="header" :text="text" theme="sale" @close='toggleModal'/>
  </div>
  

</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components:{ Modal, },
  data(){
    return{
      title:"Hello World",
      header:"Sign up for a giveaway!", 
      text:"Grab your ninja swag at half price",
      showModal:false
    }
  },
  methods:{
    /*
    handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add("active")
    },
    */
    toggleModal(){
      this.showModal = !this.showModal
    }
  },
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
