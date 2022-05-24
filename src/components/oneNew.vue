<template>

    <div class="container">
        <div style="height: 100px;"><!-- space --></div>

        <div class="d-flex flex-column align-items-center justify-content-center">
            <h1>{{info.title}}</h1>
            <p>by: {{info.by}}</p>
        </div>

        <div class="d-flex flex-column align-items-center justify-content-center">
            <h2>Comments</h2>
            <div v-for="comment in comments" :key="comment.id">
                <card-x-comment :comment="comment"></card-x-comment>
            </div>
        </div>

        <div style="height: 100px;"><!-- space --></div>

        <div class="row">
            <div class="col">
                <!-- <card-x-vue :info="info"></card-x-vue> -->
            </div>
            
        </div>
    </div>
    

</template>

<script>
//import cardXVue from './cards/cardX.vue'
import cardXComment from './cards/cardXcomment.vue'
import axios from 'axios'
    export default {
        //components: { cardXVue },
        components: { cardXComment },
        name: 'oneNew',
        data() {
            return {
                 info: {},
                 comments: []
            }
        },
        created(){

            // using the id from the URL, we will use it to especify a valor from the API
            axios.get('https://hacker-news.firebaseio.com/v0/item/' + this.$route.params.id + '.json')
            .then((res) =>{
                //going into the kids branch
                this.info = res.data
                //this.info = res.data.kids.slice(0, 20) // show me only 20 fist comments

                this.info.kids.slice(0, 20).map( id => {
                    axios.get('https://hacker-news.firebaseio.com/v0/item/' + id + '.json')
                    .then((res) => {
                        this.comments.push(res.data)
                    }).catch((axios_err) => { console.log("comments err "+axios_err);})
                })
            }).catch((axios_err) => { console.log("err "+axios_err);})
        }
    }
</script>

<style>

</style>