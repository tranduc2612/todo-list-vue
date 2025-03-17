<script setup lang="ts">
import { ref } from 'vue';
import Todo from './components/todo/Todo.vue';

const valueStr = ref("");
let editMode = ref(false);
const listTodo = ref([
  {
    id: 1,
    content: "Làm việc nhà"
  }
])

function handleAddTodo(){
  if(!valueStr.value.length){
    return
  }
  listTodo.value.push({
    id: listTodo.value.length + 1,
    content: valueStr.value
  })
  valueStr.value = ""
}

function handleClickTodo(){
  console.log('heloo coin')
}
</script>

<template>
  <h1 class="font-bold text-2xl mb-5">Todo App2</h1>
  <div class="flex mb-10">
      <input type="text" id="first_name" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-1/6 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" 
       required 
      placeholder="Nhập việc muốn làm" v-model="valueStr"
      />
      <button type="button" @click="handleAddTodo" class="ml-3 cursor-pointer text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800">
        {{ editMode ? 'Edit' : 'Add' }}
      </button>
  </div>
  <li v-for="item in listTodo">
    <Todo :content="item.content" @click="handleClickTodo"/>
  </li>
</template>

<style scoped>
</style>
