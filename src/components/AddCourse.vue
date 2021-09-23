<template >

     <div class="form-group">
        <label for="Title"></label>
        <input v-model="title" id="Title" class="form-control" type="text" placeholder="Title">
    </div>

    <div class="form-group">
        <label for="Image"></label>
        <input v-model="image" id="Image" class="form-control" type="text" placeholder="Url">
    </div>
    <div class="d-grid gap-1">
             <button  @click="newCourse" class="btn btn-block  btn-warning my-2">Add</button>
     </div>

</template>


<script>
export default {
    data() {
        return {
            title: '',
            image: ''
        }
    },
    methods:{
        newCourse(){
            let title = this.title;
            let image = this.image;

            if(title == "" || image == "") return;

            let course = {
                title,
                image
            }

           this.$emit('nadd', course);
           
           this.title = "";
           this.image  = "";
        }
    } 
}
</script>


<style >
    
</style>