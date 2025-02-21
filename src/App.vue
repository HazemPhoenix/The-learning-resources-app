<template>
  <ul class="flex flex-col items-center gap-3 w-10/12 sm:w-8/12 mx-auto">
    <LearningResources :learning-resources="learningResources" />
  </ul>
</template>

<script>
import LearningResources from "./components/learning-resources/LearningResources.vue";

export default {
  components: {
    LearningResources,
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
