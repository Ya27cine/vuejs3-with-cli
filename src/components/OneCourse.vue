<template >
  
    <div class="card my-2">
        <img class="card-img-top" :src="course.image" :alt="course.title">
        <div class="card-body">
            <h4 class="card-title">{{  course.title }}</h4>
            <p class="card-text">Lorem ipsum dolor sit amet consectetur adipisicin. Soluta, sunt neque. Ipsam.</p>
            <button class="btn btn-sm btn-danger"  @click="deleteOne(course.id)">Delete</button>
            <br>
                <span   class="badge bg-info mx-2 my-1"> {{ course.category.name }}</span>
                <hr>
         <div>  
                <span  v-for="tag in course.tags" class="badge bg-success  mx-1"> {{ tag }}</span>
         </div>   

        </div>       
    </div>

</template>
<script>
export default {
    props: ['course'],
    methods: {
        deleteOne(id){
            this.$emit('delete', id);
        }
    }
}
</script>
<style lang="">
    
</style>