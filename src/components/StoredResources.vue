<template>
    <ul>
        <AppRescources v-for="resource in resources" :key="resource.id" :title="resource.title"
            :description="resource.description" :link="resource.link" :id="resource.id">
        </AppRescources>
    </ul>
</template>

<script>
import AppRescources from './AppResources.vue'
export default {
    inject: ['resources'],
    components: {
        AppRescources
    },
}
</script>
<style>
ul {
    list-style: none;
    margin: 0;
    padding: 0;
    margin: auto;
    max-width: 40rem;
}
</style>