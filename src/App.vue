<template>
  <div id="nav">
    <router-link class="link-text" to="/">Home</router-link> |
    <router-link class="link-text" to="/about">About</router-link>
  </div>
  <router-view/>

</template>

<style>
#nav{
  background-color: #141634;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  height: 85px;
  max-width: auto;
  
}

#nav .link-text{
  text-decoration: none;
  color: white;
  font-size: 22px;
  margin-right: 10px;
}
#nav .link-text:hover{
  color: rgb(112, 112, 222);
}

</style>
