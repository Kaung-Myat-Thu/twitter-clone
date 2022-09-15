<template>
  <header class="p-4 border-b border-gray-600 flex items-center gap-4">
    <router-link to="/profile">
      <i class="fas fa-user text-emerald-500"></i>
    </router-link>
    <h2 class="text-white font-bold text-xl">{{ $route.name }}</h2>
  </header>
</template>
