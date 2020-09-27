<template>
  <!--<img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to MyMy Vue.js App"/>-->
  <SearchBox v-on:search-query="searchQuery"/>
  <Texts v-bind:texts="texts"/>
</template>

<script scoped>
    import SearchBox from './components/SearchBox.vue'
    import Texts from './components/Texts.vue'
    import axios from 'axios'

    export default {
        name: 'App',
        components: {
            SearchBox,
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
        },
        methods: {
            searchQuery(newText) {
                this.texts = [...this.texts, newText];
            },
            created() {
                //axios.get('https:jsonplaceholder.typicode.com/texts?_limit=10')
                axios.get('https://codedance-codedance.app.secoder.net/')
                    // this is where we get the search answers
                    .then(res => this.texts = res.data)
                    .catch(err => console.log(err));
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
    
    .btn {
        display: inline-block;
        border: none;
        background: #555;
        color: #fff;
        padding: 7px 20px;
        cursor: pointer;
    }
    
    .btn.hover {
        /*TODO:: this does not work */
        background: #777;
    }
</style>