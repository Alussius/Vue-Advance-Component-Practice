<template>
    <div>
        <div class="title">
            <slot name="title"></slot>
            <!-- Slots default state in case no subtitle data from the parent component -->
            <span><slot name="subtitle">No Subtitle</slot></span>
        </div>
        <hr>
        <div>
            <slot name="content"></slot>
        </div>
    </div>
</template>

<script>
export default {
    props: ['quote']
}
</script>

<style scoped>
div {
    border: 1px solid #ccc;
    box-shadow: 1px 1px 2px black;
    padding: 30px;
    margin: 30px auto;
    text-align: center;
}
span{
    color: #ccc;
}
</style>