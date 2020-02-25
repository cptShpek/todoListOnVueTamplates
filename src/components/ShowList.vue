<template>
  <div>
    <h2>Your ToDo List Here!</h2>
    <ul>
      <li v-for="(todo, index) in list" :key="todo">
        {{todo}}
        <button @click="done( todo, index, list )">Done!</button>
        <button @click="deleteItem( index, list )">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'ShowList',
  props: ['list', 'done', 'deleteItem']
}
</script>


<style scoped>
</style>
