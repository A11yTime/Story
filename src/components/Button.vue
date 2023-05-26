<template>
    <button @click="toggleButton" :aria-pressed="isDone">Add to Favorite</button>
</template>
<script>
export default{
    data(){
        return{
            isDone: false
        }
    },
    methods: {
        toggleButton(){
            this.isDone = !this.isDone
        }
    }
}
</script>
<style>
button {
    border: .5px solid gray;
    padding: 0 5px 0 5px;
    margin: 5px;
    background-color: green;
    color: #fff;
}
</style>
