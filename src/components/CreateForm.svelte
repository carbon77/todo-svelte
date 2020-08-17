<script>
  import {createEventDispatcher} from 'svelte'

  let text = ''

  const dispatch = createEventDispatcher()

  const onAddTask = () => {
    if (text) {
      dispatch('onAddTask', {
        text
      })
      text = ''
    }
  }
</script>

<form class="create-form" on:submit|preventDefault={onAddTask}>
  <input
    type="text"
    name="text"
    class="create-form__text"
    placeholder="Enter task text"
    bind:value={text}
  >
  <button type="submit" class="create-form__submit"><span class="material-icons">add</span></button>
</form>