<template>
    <div>
        <form @submit="SearchQuery">
            <input type="text" v-model="title" name="queryKey" palceholder="Enter the query...">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>

<script>
    export default {
        name: "SearchBox",
        data() {
            return {
                title: 'put in your query'
            }
        },
        methods: {
            SearchQuery(e) {
                e.preventDefault();
                const newText = {
                    id: 7,
                    title: this.title,
                    completed: false
                }

                //send up to parent
                this.$emit('search-query', newText);
                this.title = 'put in your query';
            }
        }
    }
</script>

<style scope>
    form {
        display: flex;
    }
    
    input[type="text"] {
        flex: 10;
        padding: 5px;
    }
    
    input[type='submit'] {
        flex: 2;
    }
</style>