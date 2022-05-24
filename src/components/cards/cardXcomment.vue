<template>

    <div class="my-card2 m-2">

        <div class="block-text2 p-2">
            <div class="block-author p-2">
                <p>Author: <strong> {{comment.by}} </strong> </p>
            </div>

            <p>{{comment.text}}</p>
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
        min-height: 150px;
        min-width: 350px;
        max-width: 950px;
        background-color: #141634;
        border-radius: 20px;
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
        color: white;
    }

    .block-author{
        background-color: #24285c;
        border-top-left-radius: 20px;
        border-top-right-radius: 20px;
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