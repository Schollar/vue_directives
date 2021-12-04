<template>
       <header v-if="logged_in">
           <h3>Welcome Back user!</h3>
       </header>
       <header v-else>
           Sorry You must login to continue!
           <button>Login</button>
       </header>
</template>

<script>
    export default {
        name: 'page-header',
        props: {
           logged_in: Boolean,
        }
    }
</script>

<style scoped>

</style>