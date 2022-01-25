<template>
  <div>
    <v-app-bar
      color="primary"
      dense
      dark
    >
    <v-toolbar-title>Adarsh Store</v-toolbar-title>
    <v-spacer></v-spacer>
      <router-link v-for="navlink,i in menus" :key="i"  :to="navlink.path"  class="ma-2 white--text">{{navlink.name}}</router-link>
     </v-app-bar> 
  </div>
</template>

<script>
export default {
    data(){
        return{
            menus:[
                {
                 path:'/'  ,
                 name : 'Home' 
                },
                {
                 path:'/about'  ,
                 name : 'About' 
                },
                {
                 path:'/contact-us'  ,
                 name : 'Contact us' 
                }
            ]
        }
    }
}
</script>
<style scoped>
 a{
    text-decoration: none ;
}
</style>
