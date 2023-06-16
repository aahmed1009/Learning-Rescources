<template>
    <base-card>
        <base-button @click="setSelectedTab(stored-resources)">Stored Resources </base-button>
        <base-button @click="setSelectedTab(add-resources)">Add Resources </base-button>
    </base-card>
    <component :is="selectedTab"></component>
</template>

<script>
import storedRescources from './components/StoredResources.vue'
import addResources from './components/AddRescources.vue'
export default {

    data() {
        return {
            selectedTab: 'stored-resources'
        }
    },
    methods:{
        setSelectedTab(tab){
            this.selectedTab = tab
        }
    },
    components: { storedRescources,addResources },

}
</script>

<style></style>