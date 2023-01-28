<template>
    <v-card class="mx-5 my-3 pa-4 ">
        <v-row>
            <v-col v-for="n in 200" :key="n" cols="4" sm="2" md="1"  >
                <v-hover v-slot="{ isHovering, props }">
                    <v-card :elevation="isHovering ? 16 : 1"  v-bind="props" @click="copyurl(`https://picsum.photos/10/6?image=${n * 5 + 10}${isnotgray ? '' : '&grayscale'}`)">
                        <v-img :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${isnotgray ? '' : '&grayscale'}`" 
                            :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${isnotgray ? '' : '&grayscale'}`"
                            aspect-ratio="1"
                            cover
                            class="bg-grey-lighten-2"
                        >
                            <template v-slot:placeholder>
                                <v-row class="fill-height ma-0" align="center" justify="center">
                                    <v-progress-circular  indeterminate color="grey-lighten-1">
                                
                                    </v-progress-circular>
                                </v-row>
                            </template>
                        </v-img>
                    </v-card>
                </v-hover>
            </v-col>
        </v-row>
    </v-card>
</template>

<script>
import { ref } from '@vue/reactivity'

export default {
    props:['isnotgray'],
    setup(props){
       const copyurl = async (url) =>{
        await navigator.clipboard.writeText(url)
       }


       return {copyurl}
    }
}
</script>

<style>

</style>