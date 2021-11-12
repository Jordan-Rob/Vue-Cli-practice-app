<template>
  <h1>{{ title }}</h1>
  <p>welcome...</p>
  <button @click="toggleModal">Click me</button>
  <button @click="toggleModalTwo">Newsletter</button>
  <!--<input type="text" ref="name">-->
  <!--<button @click="handleClick">Click me</button>-->
  <teleport to=".modals" v-if="showModal" >
    <modal :header="header" :text="text" theme="sale" @close='toggleModal'>
      <template v-slot:links>
        <a href="#">Sign Up</a>
        <a href="#">More info</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag at half price</p>
    </modal>
  </teleport>
  <teleport to='.modals' v-if="showModalTwo">
    <modal @close="toggleModalTwo">
      <h1>Subscribe to our Newsletter</h1>
      <p>We promise we won't spam your inbox</p>
      <template v-slot:links>
        <a href="#">Subscribe</a>
      </template>
    </modal>
  </teleport>
  

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
      showModal:false,
      showModalTwo:false
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
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo
    }
  },
}
</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
