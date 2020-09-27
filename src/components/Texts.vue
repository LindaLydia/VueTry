<template>
    <div>
        <div v-bind:key="text.id" v-for="text in texts">
            <TextItem />
        </div>
    </div>
</template>

<script>
    import TextItem from './TextItem.vue'

    export default {
        name: "Texts",
        componets: {
            TextItem
        },
        props: ["texts"]
    }
</script>

<style scoped>

</style>