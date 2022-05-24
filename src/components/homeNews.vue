<template>
    <div class="container">
        <div class="row">
            <div style="height: 100px;"><!-- space --></div>
            <div class="d-flex align-items-center justify-content-center">
                <h1>Stories home</h1>
            </div>
            <div style="height: 100px;"><!-- space --></div>

            <div class="d-flex flex-row flex-wrap justify-content-center">
                
                <div v-for="info, id in infos" :key="id">
                    <card-x-vue :info='info'></card-x-vue>
                </div>
            </div>


        </div>
    </div>
</template>

<script>
    import axios from 'axios'
    import cardXVue from './cards/cardX.vue'
    export default {
        components: { cardXVue },
        name: 'homeNews',
        data() {
            return {
                infos: [

                ]
            }

        },
        created(){
            axios.get('https://hacker-news.firebaseio.com/v0/topstories.json')
            .then((res) => {
                const resInfo = res.data.slice(0, 10) // get only 10 first stories
                // get data and put it into infos variable
                resInfo.map(id => {
                    axios.get('https://hacker-news.firebaseio.com/v0/item/'+ id + '.json')
                    .then((res) => {
                        this.infos.push(res)
                        console.log(res);
                        // information error
                    }).catch((axios_err) => {console.log("home log- "+ axios_err);})
                })
            })
        }
    }
</script>

<style>

</style>