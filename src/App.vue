<template>
  <Header />
  <main class="flex-1 overflow-scroll">
    <router-view />
  </main>
  <Footer :routes="routes" />
</template>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import { ref, onBeforeMount } from "vue";
import { useRouter } from "vue-router";

export default {
  setup() {
    const routes = ref([]);
    const router = useRouter();

    onBeforeMount(() => {
      routes.value = router.options.routes.filter((r) => r.mainMenu);
    });
    return {
      routes,
    };
  },
  components: {
    Header,
    Footer,
  },
};
</script>
