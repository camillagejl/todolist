<template>
  <div class="task">
    <button class="delete"
    @click="$emit('event', index)"
    >
      x
  </button>
    {{ task }}
  </div>
</template>

<script>
export default {
  name: "task",
  props: {
    task: String,
    index: Number
  }
}
</script>

<style scoped>
.task {
  display: block;
}
</style>