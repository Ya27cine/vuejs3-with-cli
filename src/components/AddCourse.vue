<template >

    <form @submit.prevent="newCourse"> 

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
    
        <div class="form-check">
          <label class="form-check-label">
            <input type="checkbox" class="form-check-input" v-model="published">
             Published
          </label>
        </div>
    
        <div class="my3">
            <h4> Tags</h4>
            <div class="form-check" v-for="tag in tags">
              <label class="form-check-label">
                <input type="checkbox" class="form-check-input" :value="tag" v-model="myTags">
                  {{ tag }}
              </label>
            </div>
        </div>
    
         <div class="d-grid gap-1">
            <button  class="btn btn-block  btn-warning my-2">Add</button>
        </div>
    </form>


     
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
            typeOfPayment: "free",
            published: false,
            tags: ['Framework', 'FrontEnd', 'Backend', 'JavaScript'],
            myTags:[]
        }
    },
    methods:{
        newCourse(){
            let title   = this.title;
            let image   = this.image;
            let tags  = this.myTags;
            let category = this.categories[ this.category ];


            if(title == "" || image == "") return;

            let course = {
                title,
                image,
                tags,
                category
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