<template>
        <div v-if="post">
            <h4>{{ post.title }}</h4>
            <p>{{ post.content }}</p>
        </div>
</template>
<script>
import { computed } from 'vue';
import { useRoute, useRouter } from "./../node_modules/vue-router/dist/vue-router.esm-browser.js"
import { testPosts } from './testPosts.js'

export default {
    //Option API way
    beforeRouteEnter(to, from, next) {
        console.log(to, from);
        // next();
        next('/posts');
    },
    computed: {        
        post() {
            return testPosts.find(x => x.id === parseInt(this.$route.params.id))
        }
    }

    //COMPOSITION API way
    // setup() {
    //     const route = useRoute();
    //     console.log(route.params);

    //     const post = computed(() => {
    //         const thePost = testPosts.find(x => x.id === parseInt(route.params.id));

    //         return thePost;
    //     });

    //     return {
    //         post
    //     }

    // }
}
</script>