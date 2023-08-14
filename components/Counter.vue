<template>
  <div class="flex flex-col gap-8">
    <span class="text-3xl">{{ counter }}</span>
    <div class="flex gap-4">
      <button type="button" class="py-2 px-4 rounded bg-blue-300" @click="handleCount(-10)">-10</button>
      <button type="button" class="py-2 px-4 rounded bg-blue-300" @click="handleCount(-1)">-</button>
      <button type="button" class="py-2 px-4 rounded bg-blue-300" @click="handleReset">0</button>
      <button type="button" class="py-2 px-4 rounded bg-blue-300" @click="handleCount(1)">+</button>
      <button type="button" class="py-2 px-4 rounded bg-blue-300" @click="handleCount(10)">+10</button>
    </div>
  </div>
</template>

<script setup lang="ts">
const counter = useState("counter", () => Math.round(Math.random() * 1000));

const handleCount = (num: number) => {
  counter.value += num;
};

const handleReset = () => {
  counter.value = 0;
};
</script>
