<template >

     <div class="form-group">
        <label for="Title"></label>
        <input v-model="title" id="Title" class="form-control" type="text" placeholder="Title">
    </div>

    <div class="form-group">
        <label for="Image"></label>
        <input v-model="image" id="Image" class="form-control" type="text" placeholder="Url">
    </div>
   

     <div class="form-group">
         <label for="category"></label>
         <select v-model="category" id="category" class="form-control">
             <option  
                        v-for="category in categories"
                        :value="category.id"> 
                        {{ category.name }} 
             </option>
         </select>
     </div>

     <div class="form-check form-check-inline">
        <input v-model="typeOfPayment"  class="form-check-input" type="radio" name="typeOfPayment" id="flexRadioDefault1" value="free" >
        <label class="form-check-label" for="flexRadioDefault1">
           Free
        </label>
      </div>
      <div class="form-check form-check-inline">
        <input v-model="typeOfPayment" class="form-check-input" type="radio" name="typeOfPayment" id="flexRadioDefault2" value="paying">
        <label class="form-check-label" for="flexRadioDefault2">
          Paying
        </label>
    </div>

     <div class="d-grid gap-1">
        <button  @click="newCourse" class="btn btn-block  btn-warning my-2">Add</button>
    </div>

     <div class="well my-3">
         <p>Title: {{title}}</p>
         <p>Url: {{image}}</p>
         <p>category: {{category}}</p>
         <p>typeOfpayment: {{typeOfPayment}}</p>
     </div>
</template>


<script>
export default {
    data() {
        return {
            title: '',
            image: '',
            categories: [
                {'id': 1, 'name': "FrontEnd"},
                {'id': 2, 'name': "BackEnd"},
                {'id': 3, 'name': "FullStack"},
                {'id': 4, 'name': "Mobile"},
            ],
            category: 3,
            typeOfPayment: "free"
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