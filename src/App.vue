<template>
  <div id="app">
    <h1>Welcome to Your Personal ToDo List!</h1>
    <div id="wrapper">

        <CreateList v-bind:list="list" :addTodo="addItem"/>

        <ShowList v-bind:list="list" :deleteItem="deleteItem" :done="itemDone"/>

        <DoneList v-bind:list="doneList" :deleteItem="deleteItem"/>

    </div>
  </div>
</template>

<script>

  import ShowList from './components/ShowList.vue'
  import CreateList from './components/CreateList.vue'
  import DoneList from './components/DoneList.vue'

  export default {

    name: 'App',

    data () { return{

      list: [],
      doneList: [],

    }},

    components: {

      ShowList,
      CreateList,
      DoneList

    },

    methods: {

      addItem: function( el ) {

        if ( el ) {

          this.list.push( el );
          return;

        } else {

          return alert('Enter item please!');

        }

      },

      deleteItem: function( index, thisList ) {

        thisList.splice( index, 1 );
        return;

      },

      itemDone: function( el, index, thisList ) {

        this.doneList.push( el );
        this.deleteItem( index, thisList );
        return;

      },

    }

  }
</script>

<style>
  #wrapper{
    display: flex; 
    justify-content: space-between;
    border: 5px double black;
    background: green;
  }
  #wrapper div{
    border: 4px double grey;
    background: olivedrab;
  }
  h1{
    text-align: center;
  }
  h2{
    text-align: center;
  }
  li:hover{
    background: white;
  }
  button:hover{
    background: grey;
  }
</style>
