<template>
  <ul v-for="task in tasks" :key="task">
      <li >{{task}}</li>
  </ul>
  <form>
      <input type="text" v-model="newTaskName">
      <button @click="addNewTask(newTaskName)">Add task</button>
  </form>
</template>

<script>
export default {
    data() {
        return {
            newTaskName: '',
            tasks: []
        }
    }
}
</script>

<style>

</style>