<template>
  <main class="p-3">

    <section class="flex gap-3 mb-5">
      <FwbInput type="text" name="" id="" v-model="todoInput" placeholder="Input your to do" />
      <FwbButton @click="handlerAddTodo">Add Todo</FwbButton>
    </section>

    <FwbListGroup>
      <template v-for="(todo, index) in todolists">
        <TodoList @transfer-data="(payload) => console.log(payload)"
          @remove-todo="(payload) => handlerRemoveTodo(payload)" :todo="todo" :index="index" />
      </template>
    </FwbListGroup>
  </main>
</template>

<script setup lang="ts">
import { reactive, ref } from 'vue';
import TodoList from './components/TodoList.vue';
import { FwbButton, FwbInput, FwbListGroup } from 'flowbite-vue';

// refs
const todolists = reactive([])
const todoInput = ref('')

// handler: add todo
const handlerAddTodo = () => {

  todolists.push(todoInput.value)

  todoInput.value = ""
}

// handler: remove todo
const handlerRemoveTodo = (index) => {

  todolists.splice(index, 1)
}

</script>