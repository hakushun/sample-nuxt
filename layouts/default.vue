<template>
  <div class="flex flex-col min-h-screen">
    <Header />
    <main class="flex-1 bg-gray-50 py-4 px-8">
      <slot />
    </main>
    <Footer />
  </div>
</template>
