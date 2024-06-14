<template>
    <footer>
        <button @click="() => updateTab('collection')"><img src="../assets/images/collection.png"/></button>
        <button @click="() => updateTab('map')"><img src="../assets/images/map.png"/></button>
        <button @click="() => updateTab('inventaire')"><img src="../assets/images/inventaire.png"/></button>
    </footer>
</template>

<script>
    export default {
        methods: {
            updateTab(tab) {
                this.$emit('update-tab', tab);
            }
        }
    }
</script>

<style scoped>
    footer {
        position: fixed;
        bottom:0;
        width: 100%;
        justify-content: center;
        display: flex;
        gap: 3rem;
        padding: 1rem;
        z-index: 20;
    }

    button {
        all: unset;
        max-width: 5rem;
        cursor: pointer;
    }

    button img {
        max-width: 100%;
        max-height: 100%;
    }
</style>