<script setup>
import {ref, watch, onMounted} from 'vue'

const tasks = ref([])
const newTask = ref('')


function addTask() {
  if (newTask.value.trim() === '') return

  tasks.value.push({
    id: Date.now(),
    text: newTask.value,
    done: false
  })

  newTask.value = ''
}

function removeTask(id) {
  tasks.value = tasks.value.filter(task => task.id !== id)
}

onMounted(() => {
  const saved = localStorage.getItem('tasks')
  if (saved) {
    tasks.value = JSON.parse(saved)
  }
})

watch(tasks, (newTasks) => {
  localStorage.setItem('tasks', JSON.stringify(newTasks))
}, {deep: true})

</script>

<template>
  <div>
    <h1>Minha To-do List</h1>

    <input v-model="newTask" placeholder="Digite uma tarafa"/>
    <button @click="addTask">Adicionar</button>
    
    <ul>
      <li v-for="task in tasks" :key="task.id">
        
      <input type="checkbox" v-model="task.done" />   
      
      <span :style="{ textDecoration: task.done ? 'line-through' : 'none' }">
        {{ task.text }}
      </span>
      
      <button @click="removeTask(task.id)" id="botao">X</button>
        
      </li>
    </ul>

  </div>
</template>

<style>
body {
  font-family: Arial;
}

ul {
  list-style: none;
  padding: 0;
}
#botao {
  margin: 10px

}
</style>
