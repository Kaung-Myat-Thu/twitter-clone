<template>
  <footer class="grid grid-cols-4 text-center border-t border-gray-600">
    <router-link
      v-for="(route, i) in routes"
      :key="i"
      :to="route.path"
      :class="route.name == $route.name ? 'text-emerald-500' : 'text-gray-300'"
    >
      <i :class="route.iconClass" class="text-2xl p-4"></i>
    </router-link>
  </footer>
</template>

<script>
export default {
  props: {
    routes: Array,
  },
};
</script>
