<template>
    <div>
        <div v-bind:key="text.id" v-for="text in texts">
            <TextItem v-bind:text="text"/>
        </div>
    </div>
</template>

<script>
    import TextItem from './TextItem.vue'

    export default {
        name: "Texts",
        components: {
            TextItem
        },
        props: ["texts"]
    }
</script>

<style scoped>

</style>