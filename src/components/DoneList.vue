<template>
  <div>
    <h2>Your Done List Here!</h2>
    <ul>
      <li v-for="(done, index) in list" :key="done">
          {{done}}
          <button @click="deleteItem( index, list )">Delete</button>
          </li>
    </ul>
  </div>
</template>

<script>
export default {

  name: 'DoneList',

  props: ['list', 'deleteItem'],

}
</script>


<style scoped>
</style>
