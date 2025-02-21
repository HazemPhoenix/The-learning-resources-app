<template>
  <ul class="flex flex-col items-center gap-3 border-1 w-8/12 mx-auto">
    <ResourceItem v-for="item in learningResources" :item="item" :key="item.id" />
  </ul>
</template>

<script>
import ResourceItem from "./components/learning-resources/ResourceItem.vue";
export default {
  components: {
    ResourceItem,
  },
  data() {
    return {
      learningResources: [
        {
          id: 1,
          title: "Vue.js official docs",
          description: "The official documentation for Vue.js",
          link: "https://vuejs.org",
        },
        {
          id: 2,
          title: "Maxmilian Schwarzmuller Vue.js course",
          description: "The udemy course on Vue.js by Maxmilian Schwarzmuller",
          link: "https://www.udemy.com/course/vuejs-2-the-complete-guide/",
        },
      ],
    };
  },
};
</script>
