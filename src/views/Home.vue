<template>
  <v-app>
    <!-- side nav -->

    <Sidenav :isnotgray="isnotgray" @changescale="changecolor" />

    <v-main>
      <Imagegallery :isnotgray="isnotgray" />
    </v-main>
  </v-app>
</template>

<script>
  import Sidenav from '@/components/Sidenav.vue'
  import Imagegallery from '@/components/Imagegallery.vue'
  import { ref } from '@vue/reactivity'
  export default{
    components : {Sidenav, Imagegallery},
    setup(){
      
      const isnotgray = ref(true)
      
      const changecolor = (isitgray) => {
        isnotgray.value = isitgray
      }
      
      
      return {isnotgray, changecolor}
    }
  }
</script>
