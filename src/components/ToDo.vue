<template>
  <div class="container">
    <h1 class="text-center">
      {{ title }}
    </h1>
    <form @submit.prevent="addToDo">
      <div class="form-group">
        <label for="to-do">What do you want to do?</label>
        <input v-model="newTodo" type="text" class="form-control" id="to-do" placeholder="Enter task" />
        <small id="emailHelp" class="form-text text-muted">You actually need to do it 🙃</small>
      </div>
      <button type="submit" class="btn btn-primary">Add</button>
    </form>
    <div>
      <ul v-for="(todo, index) in todos" :key="todo.id">
        <li>{{ todo.task }} <button class="btn btn-danger" @click="deleteToDo(index)">Delete</button></li>
      </ul>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'ToDo',
  props: {
    title: String
  },
  setup() {
    const newTodo = ref('');
    const todos = ref([]);
    const addToDo = () => {
      if (!newTodo.value) return alert('Please add a task');
      todos.value.push({
        id: Date.now(),
        task: newTodo.value,
        done: false
      });
      newTodo.value = '';
    };
    const deleteToDo = index => {
      todos.value.splice(index, 1);
    };
    return {
      todos,
      newTodo,
      addToDo,
      deleteToDo
    };
  }
};
</script>
