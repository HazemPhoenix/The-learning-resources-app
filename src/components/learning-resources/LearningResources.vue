<template>
  <ul class="flex flex-col items-center gap-3 w-10/12 sm:w-8/12 mx-auto">
    <LearningResourcesItem
      v-for="resource in learningResources"
      :item="resource"
      :key="resource.id"
    />
  </ul>
</template>

<script>
import LearningResourcesItem from "./LearningResourcesItem.vue";

export default {
  components: {
    LearningResourcesItem,
  },
  inject: ["learningResources"],
};
</script>
