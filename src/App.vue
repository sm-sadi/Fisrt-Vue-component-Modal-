<template>
  <div>
    <h1>{{title}} </h1>
  <!-- <input type="text" ref="names" >
  <button @click="dothis">clickme </button> -->
  </div>
  <div v-if="showModal"> 
    <Modal :header="header" :text="text" theme = 'sale' @close="toggleModal">
    <template v-slot:links>
        <a href="">signup</a>
    </template>
    </Modal>
  </div>
  <button @click="toggleModal">sign up </button>
  <br>
<!-- second  -->
<div v-if="showModal2"> 
    <Modal  @close="toggleModal2" theme = 'sale'>
    <template v-slot:links>
      <h1>20% code</h1>
        <p> smsadi.com</p>
    </template>
    </Modal>
  </div>
  <button @click="toggleModal2">20% off</button>
  
</template>

<script>
import Modal from './components/Modal.vue'


export default {
  name: 'App',
  components : {Modal},
  data(){
    return{
      title : "This is a title",
      header : "signup for discount code",
      text: "offer will end soon",
      showModal : false,
      showModal2 :false
      
    }

  },
  methods: {
     
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModal2(){ 
     this.showModal2 = !this.showModal2
    }
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
h1{
  color :rgb(20, 10, 10) ;
/* background-color: rgb(221, 60, 60); */
}
.active{
 height: 300px;
  }
button{
  margin-top: 2px;
  background: #3498db;
  border-radius: 28px;
  font-family: Arial;
  color: #ffffff;
  font-size: 20px;
  padding: 10px 20px 10px 20px;
  text-decoration: none;
}
</style>
