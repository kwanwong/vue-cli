<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-md-8 col-md-offset-2">
          <div class="panel panel-default">
            <div class="panel-heading">Vue Cli脚手架工具</div>
            <div class="panel-body">
              <todo-form :items="todos"></todo-form>
              <todo-items :items="todos" title="待办事项一"></todo-items>
              <todo-form :items="todos2"></todo-form>
              <todo-items :items="todos2" title="待办事项二"></todo-items>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Hello from './components/Hello'
import TodoItems from './components/TodoItems'
import TodoForm from './components/TodoForm'
export default {
  name: 'app',
  data: function() {
    return{
      todos: [
        {id:1, title:'Vue 1.0 第一课', completed:false},
        {id:2, title:'Vue 1.0 第二课', completed:true}
      ],
      todos2: [
        {id:3, title:'Vue 2.0 第一课', completed:false},
        {id:4, title:'Vue 2.0 第二课', completed:true}
      ]
    }
  },
  components: {
    TodoItems, TodoForm
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
