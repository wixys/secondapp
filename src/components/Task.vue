<template>
	<h1>Task</h1>
	<button v-if="taskList.length" @click="clear">Clear</button>
  <input type="text" v-model="task" ref="task">
  <button @click="addTask" :disabled="isDisabled">Add</button>
  <ul>
    <li v-for="(task, index) in taskList" :key="index">
      {{ task.name }}
    </li>
  </ul>
</template>

<script>
export default {
	name: 'Task',
	data() {
		return {
			task: '',
      taskList: [],
		}
	},
	mounted: function() {
    this.focus()
  },
	methods: {
		addTask() {
      this.taskList.push({ name: this.task })
      this.task = ''
      this.focus()
    },
    clear() {
      this.taskList = []
    },
    focus() {
      this.$refs.task.focus()
    }
	},
	computed: {
    isDisabled() {
      if(this.task.length >= 5) {
        return !this.task
      }
      return true
    }
  }
}
</script>