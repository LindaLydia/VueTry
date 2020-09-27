<template>
    <div class='text-item' v-bind:class="{'is-complete':text.completed}">
        <p>{{text.title}}</p>
    </div>
</template>

<script>
    export default {
        name: "TextItem",
        props: ["text"]
    }
</script>

<style scoped>
    .text-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }
    
    .is-complete {
        text-decoration: line-through;
    }
    
    .is-highlighted {
        text-decoration-color: steelblue;
    }
</style>