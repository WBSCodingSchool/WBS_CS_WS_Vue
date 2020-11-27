<template>
  <h1 class="text-center">{{title}}</h1>
  <form  v-on:submit.prevent="addToDo">
  <div class="form-group">
    <label for="to-do">What do you want to do?</label>
    <input v-model="newToDo" type="text" class="form-control" id="to-do" placeholder="Enter task">
    <small id="emailHelp" class="form-text text-muted">You actually need to do it 🙃</small>
  </div>
  <button type="submit" class="btn btn-primary">Add</button>
  <div>
    <ul v-for="todo in todos" v-bind:key="todo.id">
      <li>{{todo.task}}</li>
    </ul>
  </div>
</form>
</template>

<script>
import {ref} from 'vue';

export default {
  name: 'ToDo',
  props: {
    title: String
  },
  setup(){
    const newToDo = ref('');
    const todos = ref([]);

    const addToDo = () => {
     todos.value.push({id: Date.now(), task: newToDo.value, done: false});
     newToDo.value = '';
    }
    return{
      newToDo,
      todos,
      addToDo
    }
  }
}
</script>

<style scoped>

</style>
