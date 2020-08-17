<script>
  import './styles/index.css'
  import CreateForm from './components/CreateForm.svelte'
  import TaskList from './components/TaskList.svelte'

  let tasks = []

  const addTask = ({ detail }) => {
    tasks = [...tasks, {
      id: tasks.length + 1,
      text: detail.text,
      completed: false
    }]
  }
</script>

<div class="app">
  <div class="content">
    <div class="header">
      <h1>Svelte tasks</h1>
    </div>

    <CreateForm on:onAddTask={addTask} />

    <TaskList {tasks} />
  </div>
</div>