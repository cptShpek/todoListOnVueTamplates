<template>
  <div>
        <h2>Create your ToDo List!</h2>
        <input type="text" v-model="inputValue"><button @click="addTodo( inputValue )">Add Item!</button>
  </div>
</template>

<script>
    export default {

        name: 'CreateList',

        props: ['list', 'addTodo'],

        data() { return {

            inputValue: [],

        }},
    }
</script>


<style scoped>
</style>
