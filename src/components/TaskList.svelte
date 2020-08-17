<script>
  import TaskItem from './TaskItem.svelte'

  export let tasks

  const onToggleTask = ({ detail }) => {
    tasks = tasks.map(task => {
      if (task.id === detail.id) {
        return { ...task, completed: !task.completed }
      }
      return task
    })
  }

  const onRemoveTask = ({ detail }) => {
    tasks = tasks.filter(task => task.id !== detail.id)
  }
</script>

<ul class="task__list">
  {#each tasks as task}
    <TaskItem {task} on:onToggleTask={onToggleTask} on:onRemoveTask={onRemoveTask} />
  {/each}
</ul>