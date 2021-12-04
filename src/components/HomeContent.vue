<template>
    <div v-on="change_mode(dark_mode)">
        <button @click="dark_mode = !dark_mode">Dark/Light Mode</button>
      <page-header :logged_in="logged_in"></page-header>
      <page-post v-for=" post in user_posts" :key="post.post_id" :post="post.content"></page-post>  
    </div>
</template>

<script>
import PagePost from './PagePost.vue'
import PageHeader from './PageHeader.vue';
    export default {
        name: 'home-content',
        components: {
            PageHeader,
            PagePost,
        },
        methods: {
            change_mode(bool) {
                if(bool) {
                    document.body.style.backgroundColor = 'black';
                    document.body.style.color = 'white';
                } else {
                    document.body.style.backgroundColor = 'white';
                    document.body.style.color = 'black';
                }
            }
        },
        data() {
            return {
                dark_mode: true,
                logged_in: false,
                user_posts: [
                    {
                        post_id: 1,
                        content: "This is the first post!"
                    },
                     {
                        post_id: 2,
                        content: "This is the second post!"
                    },
                     {
                        post_id: 3,
                        content: "This is the third post!"
                    },
                ]
            }
        },
    }
</script>

<style scoped>

</style>