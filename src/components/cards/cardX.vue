<template>

    <div class="my-card m-2">
        <div class="block-title p-2">
            <h3> <router-link id="link" :to="{path: '/oneNew/'+ info.data.id}">{{info.data.title}}</router-link></h3>
        </div>
        
        <div class="block-text p-2">
            <p>by: {{info.data.by}}</p>
            <p>time: {{info.data.time}}</p>
        </div>
    </div>

</template>

<script>
    export default {
        name: 'cardX',
        props:['info']
    }
</script>

<style scoped>
    .my-card {
        min-height: 150px;
        min-width: 350px;
        max-width: 400px;
        background-color: #141634;
        border-radius: 20px;
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    }
    .block-text{
        background-color: rgb(167, 181, 219);
        height: auto;
        border-bottom-left-radius: 20px;
        border-bottom-right-radius: 20px;
    }
    .block-title{
        display: flex;
        flex-direction: row;
        justify-content: center;
    }
    .block-title #link{
        color: white;
        text-decoration: none;
        
    }
    .block-title #link:hover{
        color: rgb(112, 112, 222);
        text-decoration: none;
        
    }
</style>