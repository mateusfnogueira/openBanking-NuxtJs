<template>
  <v-app dark>
    <Header />
    <v-footer class="d-flex justify-center" app>
      <span class="mr-4">Desenvolvido por - Mateus Nogueira</span>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
import Header from "../components/Header";

export default {
  components: { Header }
};
</script>
