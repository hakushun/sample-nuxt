<template>
  <header class="flex w-full justify-between py-4 px-8 bg-gray-200">
    <h1>Nuxt Sample</h1>
    <nav>
      <ul class="flex gap-4">
        <li><NuxtLink to="/" class="p-2">Home</NuxtLink></li>
        <li><NuxtLink to="/counter" class="p-2">Counter</NuxtLink></li>
        <li><NuxtLink to="todo" class="p-2">Todo</NuxtLink></li>
        <li><NuxtLink to="album" class="p-2">Album</NuxtLink></li>
      </ul>
    </nav>
  </header>
</template>
