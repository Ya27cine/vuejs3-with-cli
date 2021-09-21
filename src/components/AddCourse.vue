<template >

     <div class="form-group">
        <label for="Title"></label>
        <input ref="title" id="Title" class="form-control" type="text">
    </div>

    <div class="form-group">
        <label for="Image"></label>
        <input ref="image" id="Image" class="form-control" type="text">
    </div>
    <div class="d-grid gap-1">
             <button  @click="newCourse" class="btn btn-block  btn-warning my-2">Add</button>
     </div>
    

    


</template>


<script>
export default {


    methods:{
        newCourse(){
            let title = this.$refs.title.value;
            let image = this.$refs.image.value;

            if(title == "" || image == "") return;

            let course = {
                title,
                image
            }

           this.$emit('nadd', course);
           
           this.$refs.title.value  = "";
           this.$refs.image.value  = "";
        }
    }
    
}
</script>


<style >
    
</style>