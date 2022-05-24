<template>
  <div class="home">
    
    <home-news></home-news>
  </div>
</template>

<script>
import homeNews from '../components/homeNews.vue'
// @ is an alias to /src


export default {
  components: { homeNews },
  name: 'Home',

}
</script>
