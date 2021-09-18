<template >
  
    <div class="card my-3">
        <img class="card-img-top" :src="course.image" :alt="course.title">
        <div class="card-body">
            <h4 class="card-title">{{  course.title }}</h4>
            <p class="card-text">Text</p>
        </div>
    </div>

</template>
<script>
export default {
    props: ['course']
}
</script>
<style lang="">
    
</style>