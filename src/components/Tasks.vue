<template>
  <ul >
      <li v-for="(task, index) in tasks" :key="task">{{task}}  <font-awesome-icon @click="deleteTask(index)" :icon="['fas', 'trash']" class="red" />

 </li>
  </ul>
  <form>
      <input type="text" v-model="newTaskName">
      <button @click.prevent="addNewTask()">Add task</button>
  </form>
</template>

<script>

export default {
    data() {
        return {
            newTaskName: '',
            tasks: []
        }
    },
    methods: {
        addNewTask() {
            if(this.newTaskName != '') {
                this.tasks.push(this.newTaskName)
                this.newTaskName = ''
            }
        },
        deleteTask(task) {
            console.log(task);
            this.tasks.splice(task, 1)
        }
    }
}
</script>

<style scoped>
    input, button {
        border: none;
        border-bottom: 1px solid gray;
        padding: 10px;
    }
    button {
        cursor: pointer;
        color: white;
        background: purple;
    }
    li {
        list-style: none;
        color: white;
        font-weight: bold;
        letter-spacing: 1px;
        padding: .2rem .2rem;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    ul {
        margin: auto;
        padding:0;
        width: 75%;
    }
    li:nth-child(odd) {
        background: purple;
    }
    li:nth-child(even) {
        background: white;
        color: black;
    }
    .red{
        color: black;
    }
</style>