<template>

    <div class="my-card2 m-2">

        <div class="block-text2 p-2">
            <div class="block-author p-2">
                <p>Author: <strong> {{comment.by}} </strong> </p>
            </div>
            <div class="block-text-inside p-2">
                <p>{{comment.text}}</p>
            </div>

        </div>
    </div>

</template>

<script>
    export default {
        name: 'cardXcomment',
        props: ['comment']
    }
</script>

<style scoped>
    .my-card2 {
        display: flex;
        flex-wrap: wrap;
        min-height: 150px;
        min-width: 300px;
        max-width: 950px;
        max-height: auto;
        background-color: #141634;
        border-radius: 20px;
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
        color: white;
    }

    .block-author{
        background-color: #24285c;
        border-top-left-radius: 20px;
        border-top-right-radius: 20px;
        max-height: 200px;
    }

    .block-text-inside p{
        max-height: auto;
        min-height: 150px;
        word-break: break-all;
    }

    .block-title2 {
        display: flex;
        flex-direction: row;
        justify-content: center;
    }

    .block-title2 #link {
        color: white;
        text-decoration: none;

    }

    .block-title2 #link:hover {
        color: rgb(0, 68, 255);
        text-decoration: none;

    }
</style>