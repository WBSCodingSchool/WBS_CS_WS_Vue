<template>
  <h1 class="text-center">{{title}}</h1>
  <form  v-on:submit.prevent="addToDo">
  <div class="form-group">
    <label for="to-do">What do you want to do?</label>
    <input v-model="newToDo" type="text" class="form-control" id="to-do" placeholder="Enter task">
    <small id="emailHelp" class="form-text text-muted">You actually need to do it 🙃</small>
  </div>
  <button type="submit" class="btn btn-primary">Add</button>
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

    const addToDo = () => {
      console.log(newToDo.value)
    }
    return{
      newToDo,
      addToDo
    }
  }
}
</script>

<style scoped>

</style>
