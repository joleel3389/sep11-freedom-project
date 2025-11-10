<script setup>
    /*
    import {ref} from 'vue'
    const name = ref('Jolee')
    const emoji = ref('✌🏻')
    const year = ref('2030')
    */

    import Header from '@/components/Header.vue'
    import Main from '@/components/Main.vue'
    import Footer from '@/components/Footer.vue'
</script>

<template>
    <Header/>
    <Main/>
    <Footer/>
    <!--
    <header>
        <span>{{emoji}}</span>
    </header>
    -->

    <!--
    <main>
        <h1>Hello, {{name}}!</h1>
        <p>I'm about to learn <a href="https://vuejs.org/" target="_blank">Vue.js</a>!</p>
    </main>
    -->

    <!--
    <footer>
        <p> &copy; {{year}} </p>
    </footer>
    -->
</template>

<style scoped>
    /*
    header span{
        font-size:3rem;
    }
    */

    /*
    main h1{
        display:block;
    }
    main a{
        color: #42B883;
    }
    */

    /*
    footer {
        position:fixed;
        bottom:0;
        padding-bottom:20px;
    }
    footer p{
        color:blue;
    }
    */
</style>
