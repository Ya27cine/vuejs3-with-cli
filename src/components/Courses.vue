<template >

    <div class="row" v-if="showForm">
        <div class="col-md-6 mx-auto">
            <AddCourse @nadd="addCourse($event)"  />
        </div>
    </div>

    <div class="row">
        <div class="col-md-6">
            <nav style="--bs-breadcrumb-divider: '>';" aria-label="breadcrumb">
                <slot>  </slot>
            </nav>
            <h1>List of Courses</h1>
        </div>

        <div class="col-md-6 text-end">
            <button  
                    @click="displayForm"
                    class="btn btn-sm "
                    :class="{'btn-success': !showForm, 'btn-dark': showForm}">
                  {{ (showForm)? 'Close':'New'}}
                </button>
        </div>
    </div>
    
    <div class="row">
        <div class="col-md-4"  v-for="course in courses">

            <OneCourse :course="course" 
                        @delete="deleteOneCourse($event)" 
            />
            
        </div>
    </div>

    <teleport to="#alert" v-if="courseDeleted"> 
        <div class="alert alert-danger text-center" >
            <strong>Course is deleted !</strong>
        </div>
    </teleport>

    <teleport to="#alert" v-if="courseAdded"> 
        <div class="alert alert-success text-center" >
            <strong>Course is Added successfuly !</strong>
        </div>
    </teleport>
   

</template>



<script>
    import OneCourse from './OneCourse';
    import AddCourse from './AddCourse.vue';

export default {
    components: {
        OneCourse,
        AddCourse
    },
    data() {
        return {
            showForm: false,
            courseDeleted: false,
            courseAdded: false,
            courses:[
                {
                    id: 1, 
                    title: "Learn ReactJS",
                    image: "https://ih1.redbubble.net/image.1045049975.0131/poster,504x498,f8f8f8-pad,600x600,f8f8f8.jpg",
                    category: {'id': 1, 'name': "FrontEnd"},
                    tags: ['Backend', 'FrontEnd'],
                },
                {
                    id: 2, 
                    title: "Learn Spring Boot",
                    image: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse3.mm.bing.net%2Fth%3Fid%3DOIP.WdsfOLMi-xg3DeBmn6Ev1gHaFV%26pid%3DApi&f=1",
                    category: {'id': 2, 'name': "BackEnd"},
                    tags: ['Backend'],
                },
                {
                    id: 3, 
                    title: "Learn Symfony",
                    image: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.explicit.bing.net%2Fth%3Fid%3DOIP.7aN_24cA5HAG-7yUvDNlDQHaHa%26pid%3DApi&f=1",
                    category: {'id': 4, 'name': "Mobile"},
                    tags: ['Backend'],
                },
            ]
        }
    },
    methods:{
        deleteOneCourse(id){
            alert('delete from paranet'+id)
            this.courses =  this.courses.filter( function(course){
                    return course.id != id
            });
            this.courseDeleted = true;

            setTimeout(() => { this.courseDeleted = false; }, 3000);
        },
        addCourse(course){
          //  let id = Math.max.apply(Math, this.courses.map(function(c) { return c.id; })) + 1;
          let id = Math.max(  
                            ...this.courses.map(function(c) { return c.id; }) 
                    ) + 1;
        
            course = {
                id,
                ...course
            }
            this.courses = [course, ...this.courses];
            this.showForm = false;

            this.courseAdded = true;

            setTimeout(() => { this.courseAdded = false; }, 3000);
        },
        displayForm(){
            this.showForm = ! this.showForm;
        }
    }
}
</script>


<style scoped>
h1{
    color: brown;
  }
</style>