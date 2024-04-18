<template> <!--this a vue tag we can have as meany root element as we wish-->
  <h1>{{ title }}</h1>
  <input type="text" ref="name">
  <p>welcome...</p>


  <teleport to=".modals" v-if="showModal"><!-- we are teleporting the modals into the div in our index.html with the class modals-->
    <Modal  theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>CARPE DIEM</h1>
      <p>Carpe diem even if it kills me</p>
    </Modal>
    <!-- we have created an event that starts when we click on the modal and when the event starts we want to start the function toggleModal-->
  </teleport>

  <teleport to=".modals" v-if="showModalTwo">
    <Modal  @close="toggleModalTwo"> <!--reusing a component in vue.js-->
      <h1>Sign up to the news letter</h1>
      <p>For updates and promo cod e</p>
    </Modal>
    <!-- we have created an event that starts when we click on the modal and when the event starts we want to start the function toggleModal-->
  </teleport>
  
  <button @click="toggleModal">open Modal</button> <!-- we can use click with any key we want (events modifier) click.shif , click.right , click.self-->
  <button @click="toggleModalTwo">open the second Modal</button> <!-- we can use click with any key we want (events modifier) click.shif , click.right , click.self-->

</template>


<script>
import Modal from "./components/Modal.vue"
// we import the component here by using javascript 
// this like the data we did before 
export default { // templates refs 
  name: 'App', // we can give it a name
  components: {
    Modal
  },
  data() { // it is optional to have this object but used a lot
    return {
      title:'my first vue app',
      showModal: false,
      showModalTwo:false
    }
  },
  methods:{
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo
    }
  }
  
  
 
}

</script>
 
<!--this styles ar eglobal-->
<style >
#app ,.modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body{
  margin: 0;
  padding: 0; 
  box-sizing: border-box;
  }
button{
  cursor:pointer
}
</style>
