<template >
    <div class="row">
        <div class="col-md-4"  v-for="course in courses">

                <div class="card my-3">
                    <img class="card-img-top" :src="course.image" :alt="course.title">
                    <div class="card-body">
                        <h4 class="card-title">{{  course.title }}</h4>
                        <p class="card-text">Text</p>
                    </div>
                </div>

        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
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
}
</script>
<style >
    
</style>