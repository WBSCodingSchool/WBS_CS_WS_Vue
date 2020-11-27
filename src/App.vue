<template>
  <div class="container">
    <ToDo title="ToDo App (but with Vue)"/>
  </div>
</template>

<script>
import ToDo from './components/ToDo'

export default {
  name: 'App',
  components: {
    ToDo
  }
}
</script>