<template>

   <Header />

    <div class="container">
     

      <Courses> 

        <ol class="breadcrumb">
          <li class="breadcrumb-item"><a href="#">Home</a></li>
          <li class="breadcrumb-item active" aria-current="page">List courses</li>
        </ol>

      </Courses >
      
    </div>

    <Footer 
              url="https://www.eprostam.com"  
              title="SASU PROSTAM"  
              text="Conseil Informatique"  
    />

</template>

<script>

import Header from './components/Header.vue';
import Courses from './components/Courses.vue';
import Footer from './components/Footer.vue';


export default {
  name: 'App',

  components: {
    Header, 
    Courses,
    Footer
  },

  data(){
    return {
      message: "Samphone Reparation",
      isShow: false
    }
  },
    methods: {
      handClic(){
        console.log( this.$refs.book.value);
        this.$refs.book.classList.add('active');
        this.$refs.book.focus();

      }
    },
  
        
  }
</script>

<style>

</style>
