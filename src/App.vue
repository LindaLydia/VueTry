<template>
  <!--<img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to MyMy Vue.js App"/>-->
  <Texts v-bind:texts="texts"/>
</template>

<script>
    import Texts from './components/Texts.vue'

    export default {
        name: 'App',
        components: {
            Texts
        },
        data() {
            return {
                // the news searched
                texts: [{
                    id: 1,
                    title: "Texts:1",
                    completed: false
                }, {
                    id: 2,
                    title: "Texts:2",
                    completed: true
                }, {
                    id: 1,
                    title: "Texts:3",
                    completed: false
                }]
            }
        }
    }
</script>

<style>
    /*
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
    */
    
    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }
    
    body {
        font-family: Arial, Helvetica, sans-serif;
        line-height: 1.4;
    }
</style>