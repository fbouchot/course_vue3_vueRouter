<template>  
    <h4>Posts</h4>
    <router-link
        v-for="post in testPosts" 
        :key="post"
        :to="`/posts/${post.id}`">     
        {{ post.title }}   
    </router-link>    
    <router-view/>
</template>

<script>
import { watchEffect } from 'vue'
import { testPosts } from './testPosts.js'
import { useRoute } from "./../node_modules/vue-router/dist/vue-router.esm-browser.js"
export default {
    // watch: {
    //     '$route': {
    //         handler: (val, oldVal) => {
    //             console.log(val),
    //             this.fetchData(val.params.id)
    //         },
    //         immediate: true
    //     }
    // },
    setup() {        
        return {
            testPosts
        }
    }    
}
</script>