<template>
    <h1>{{title}}</h1>
    <input type="text" ref="name">
    <button @click="handleClick">click me</button>
    <br>
    <p>Welcome...</p>
    <div v-if="showModal">
      <!-- <Modal :header="header" :text="text" theme="sale" @close="toggoleModal" /> -->
       <Modal  theme="sale" @close="toggoleModal">
         <template v-slot:links>
           <a href="">Sign Up Now</a>
            <a href="">Sign Up Now</a>
         </template>
         <h1>Ninja Giveway</h1>
         <p>Give your ninja swag for half price</p>
       </Modal>
    </div>

    <div v-if="showModalTwo">
    
       <Modal   @close="toggoleModalTwo">
         <template v-slot:links>
           <h1>Sign up to the newsletter</h1>
            <a href="">For updates and promo codes</a>
         </template>
         <h1>Ninja Giveway</h1>
         <p>Give your ninja swag for half price</p>
       </Modal>
    </div>
    <button @click.shift="toggoleModal">Open Modal (shift +click)</button> 
    <button @click="toggoleModalTwo">Open Modal </button>  
</template>

<script>
import Modal from './components/Modal.vue'
export default{
  name: 'App',
  components:{
    Modal,
  },
  data(){
    return{
      title: 'This is my first app',
      header: 'Sign up for the Giveway',
      text: 'Grab your ninja swag for half price',
      showModal: false,
      showModalTwo:false
    }
   
  },
   methods:{
      handleClick(){
        console.log(this.$refs.name);
        this.$refs.name.classList.add('active');
       
      },
      toggoleModal(){
        this.showModal = !this.showModal
      },

      toggoleModalTwo(){
        this.showModalTwo = !this.showModalTwo
      }
    }
}
</script>


<style>



</style>
