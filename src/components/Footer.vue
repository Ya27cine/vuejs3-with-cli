<template >
    <div class="card text-center">
        <div class="card-header">
            {{ text }}
        </div>
        <div class="card-body">
            <blockquote class="blockquote mb-0">
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
            <footer class="blockquote-footer"> {{ title}}  <a :href="url">{{ text }}</a> </footer>
            </blockquote>
        </div>
    </div>
  
</template>
<script>
export default {
    props: ['url', 'title', 'text']
    
}
</script>
<style >
    
</style>