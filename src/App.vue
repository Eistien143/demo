<template>
  <v-app >
    <Appbar/>
    <router-view />
  </v-app>
</template>

<script>
import Appbar from '@/components/Navbar.vue'
export default {
  components:{
    Appbar
  }
  
}
</script>

<style>

</style>
