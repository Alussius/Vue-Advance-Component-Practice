<template>
    <div>
        <h3>New Quotes</h3>
        <button @click="counter++">New</button>
        <p>{{ counter }}</p>
    </div>
</template>

<script>
export default {
    data() {
        return { counter: 0 };
    },
    destroyed() {
        console.log("New Component has been destroyed!");
    },
    deactivated() {
        console.log("Deactivated New Component");
    },
    activated() {
        console.log("Activated New Component");
    }
}
</script>

<style>
</style>