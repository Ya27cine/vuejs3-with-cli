<template>

   <Header />

    <div class="container">
      <div class="row">
        <div class="col-md-6 mx-auto text-center">

              <img alt="Vue logo" src="./assets/logo.png">
              <h1>   {{ message }}   </h1>

              <AddCourse />
             
        </div>
      </div>

      <Courses />
    </div>

    <Footer url="https://www.eprostam.com"  title="SASU PROSTAM"  text="Conseil Informatique"  />

</template>

<script>

import Header from './components/Header.vue';
import AddCourse from './components/AddCourse.vue';
import Courses from './components/Courses.vue';
import Footer from './components/Footer.vue';


export default {
  name: 'App',

  components: {
    Header, 
    AddCourse, 
    Courses,
    Footer
  },

  data(){
    return {
      message: "Samphone Reparation"
    }
  },
    methods: {
      handClic(){
        console.log( this.$refs.book.value);
        this.$refs.book.classList.add('active');
        this.$refs.book.focus();

      }
    }
  }
</script>

<style>

</style>
