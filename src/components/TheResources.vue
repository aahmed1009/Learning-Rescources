<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')" :mode="storedResultButtonMode">Stored
            Resources
        </base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addToStoreResultButtonMode">Add Resources </base-button>
    </base-card>
    <component :is="selectedTab"></component>
</template>

<script>
import AddResource from './AddResources.vue';
import storedResources from './StoredResources.vue';
export default {
    components: { AddResource, storedResources },

    data() {
        return {
            selectedTab: 'stored-resources',
            storedResources: [
                {
                    id: 'official-guide',
                    title: 'Official Guide',
                    description: 'The official Vue.js documentation.',
                    link: 'https://vuejs.org',
                },
                {
                    id: 'google',
                    title: 'Google',
                    description: 'Learn to google...',
                    link: 'https://google.org',
                },
            ],
        };
    },
    provide() {
        return {
            resources: this.storedResources,
        };
    },
    computed: {
        storedResultButtonMode() {
            return this.selectedTab === 'stored-resources' ?
                null :
                'flat';
        },
        addToStoreResultButtonMode() {
            return this.selectedTab === 'add-resource' ?
                null :
                'flat';
        },
    },

    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab;
        },
    },


}
</script>

<style></style>