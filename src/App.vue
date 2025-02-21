<template>
  <TheHeader />
  <LearningResources :learning-resources="learningResources" />
</template>

<script>
import TheHeader from "./components/layouts/TheHeader.vue";
import LearningResources from "./components/learning-resources/LearningResources.vue";

export default {
  components: {
    LearningResources,
    TheHeader,
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
