<template>
    <v-navigation-drawer rail expand-on-hover rail-width="55" color="grey-lighten-2 text-blue-darken-4">
        <v-list>
            <v-list-item prepend-avatar="../assets/userimg.jfif" title="Samuel Hydra" subtitle="samdra-223@gmail.com">
            </v-list-item>

            <v-divider></v-divider>

            <v-list>
                <v-list-item prepend-icon="mdi-image" title="Color Gallery" value="color" @click="changescale(true)" />
                <v-list-item prepend-icon="mdi-dialpad" title="Grayspace Gallery" value="colors" @click="changescale(false)" />
            </v-list>
        </v-list>
    </v-navigation-drawer>
</template>
<script>
import { ref } from '@vue/reactivity'
import { defineEmits } from 'vue'
export default {
    props: ["isnotgray"],

    methods:{
        changescale(isitgray){
            this.$emit('changescale', isitgray)
        }
    }
}
</script>
<style>
    
</style>