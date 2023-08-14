<template>
  <div class="flex flex-col gap-8">
    <form class="flex gap-4" @submit.prevent="handleSubmit">
      <input type="text" name="todo" class="py-1 px-2 rounded" v-model="todo" />
      <button type="submit" class="px-4 bg-orange-300 rounded">CREATE</button>
    </form>
    <ul class="flex flex-col gap-2">
      <li v-for="todo in todos" :key="todo.id" class="flex gap-8">
        <span>{{ todo.todo }}</span>
        <button type="button" class="px-2 bg-orange-200 rounded" @click="handleDelete(todo.id)">delete</button>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
type Todo = {
  id: number;
  todo: string;
};
const todo = useState("todo", () => "");
const todos = useState<Todo[]>("todos", () => []);

const handleSubmit = () => {
  function generateId(todos: Todo[]) {
    const last = todos.at(-1);
    if (!last) return 1;
    return last.id + 1;
  }

  todos.value.push({ id: generateId(todos.value), todo: todo.value });
  todo.value = "";
};

const handleDelete = (id: number) => {
  todos.value = todos.value.filter((todo) => todo.id !== id);
};
</script>
