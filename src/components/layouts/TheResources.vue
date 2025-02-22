<template>
  <BaseCard align-buttons="center" class="mb-5">
    <template #buttons>
      <BaseButton
        @click="changeSelectedTab('LearningResources')"
        :color="selectedTab === 'LearningResources' ? 'bg-blue-950' : 'bg-blue-800'"
        >Stored Resources</BaseButton
      >
      <BaseButton
        @click="changeSelectedTab('AddResources')"
        :color="selectedTab === 'AddResources' ? 'bg-blue-950' : 'bg-blue-800'"
        >Add Resources</BaseButton
      >
    </template>
  </BaseCard>
  <KeepAlive>
    <component :is="selectedTab"></component>
  </KeepAlive>
</template>

<script>
import AddResources from "../learning-resources/AddResources.vue";
import LearningResources from "../learning-resources/LearningResources.vue";
import BaseButton from "../UI/BaseButton.vue";
import BaseCard from "../UI/BaseCard.vue";

export default {
  data() {
    return {
      selectedTab: "LearningResources",
      learningResources: [
        {
          title: "Vue.js official docs",
          description: "The official documentation for Vue.js",
          link: "https://vuejs.org",
        },
        {
          title: "Maxmilian Schwarzmuller Vue.js course",
          description: "The udemy course on Vue.js by Maxmilian Schwarzmuller",
          link: "https://www.udemy.com/course/vuejs-2-the-complete-guide/",
        },
      ],
    };
  },
  components: {
    BaseCard,
    BaseButton,
    LearningResources,
    AddResources,
  },
  provide() {
    return {
      learningResources: this.learningResources,
      addResource: this.addResource,
    };
  },
  methods: {
    changeSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(resource) {
      this.learningResources.unshift(resource);
    },
  },
};
</script>
