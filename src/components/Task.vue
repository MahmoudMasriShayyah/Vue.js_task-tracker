<template>
  <div @dblclick="$emit('toggle-reminder')" :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>{{ task.text }} <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i></h3>  
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object
  },
}
</script>

<style scope>
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
  border: 1px solid #ddd;
}

.fas {
  color: red;
}

.task.reminder {
  border-left: 5px solid blue;
}

.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>