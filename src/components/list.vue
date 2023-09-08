<template>
  <div class="new_task">
    <input type="text"
           v-on:keyup.enter="addTask"
           v-model="newTask"
    >
  </div>

  <div class="tasks">
  <task
      v-for="(task, index) in tasks"
      :task="task"
      :index="index"
      @event="deleteTask"
  ></task>
  </div>
</template>

<script>
import Task from "@/components/task.vue";

export default {
  name: "list",
  components: {Task},
  data() {
    return {
      tasks: [
        'Laundry',
        'Coding',
        'Fold laundry'
      ],
      newTask: ''
    }
  },
  methods: {
    addTask() {
      this.tasks.push(this.newTask);
      this.newTask = '';
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    }
  }
}
</script>

<style scoped>

</style>