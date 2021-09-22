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
            courses:[
                {
                    id: 1, 
                    title: "Learn ReactJS",
                    image: "https://ih1.redbubble.net/image.1045049975.0131/poster,504x498,f8f8f8-pad,600x600,f8f8f8.jpg"
                },
                {
                    id: 2, 
                    title: "Learn Spring Boot",
                    image: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse3.mm.bing.net%2Fth%3Fid%3DOIP.WdsfOLMi-xg3DeBmn6Ev1gHaFV%26pid%3DApi&f=1"
                },
                {
                    id: 3, 
                    title: "Learn Symfony",
                    image: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.explicit.bing.net%2Fth%3Fid%3DOIP.7aN_24cA5HAG-7yUvDNlDQHaHa%26pid%3DApi&f=1"
                },
                {
                    id: 4, 
                    title: "Learn VueJs",
                    image: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi1.wp.com%2Fblog.applibot.co.jp%2Fwp-content%2Fuploads%2F2017%2F07%2Fvuejs-logo.jpg%3Ffit%3D300%252C183%26ssl%3D1&f=1&nofb=1"
                },
                {
                    id: 5, 
                    title: "Learn Laravel",
                    image: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.secret-source.eu%2Fwp-content%2Fuploads%2F2017%2F11%2FLaravel-logo.jpg&f=1&nofb=1"
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
        },
        addCourse(course){
            this.courses = [course, ...this.courses]
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