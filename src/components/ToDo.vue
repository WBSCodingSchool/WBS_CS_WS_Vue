<template>
  <h1 class="text-center">{{title}}</h1>
  <form>
  <div class="form-group">
    <label for="to-do">What do you want to do?</label>
    <input type="text" class="form-control" id="to-do" placeholder="Enter task">
    <small id="emailHelp" class="form-text text-muted">You actually need to do it 🙃</small>
  </div>
  <button type="submit" class="btn btn-primary">Add</button>
</form>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    title: String
  }
}
</script>

<style scoped>

</style>
