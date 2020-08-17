<script>
  import {createEventDispatcher} from 'svelte'

  export let task

  const dispatch = createEventDispatcher()

  const onToggleTask = () => {
    dispatch('onToggleTask', { id: task.id })
  }

  const onRemoveTask = () => {
    dispatch('onRemoveTask', { id: task.id })
  }
</script>

<li class="task__item">
  <label class="task__toggle">
    <input type="checkbox" name="completed" checked={task.completed} on:change={onToggleTask}>
    <span class="material-icons">done</span>
  </label>
  <p class="task__text"><span>{task.text}</span></p>
  <button class="task__remove" on:click={onRemoveTask}><span class="material-icons">delete</span></button>
</li>