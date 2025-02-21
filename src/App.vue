<template>
  <TheHeader />
  <TheResources class="mb-5" align-buttons="center" />
</template>

<script>
import TheHeader from "./components/layouts/TheHeader.vue";
import TheResources from "./components/layouts/TheResources.vue";

export default {
  components: {
    TheHeader,
    TheResources,
  },
  data() {
    return {};
  },
};
</script>
