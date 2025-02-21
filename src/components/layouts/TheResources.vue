<template>
  <BaseCard align-buttons="center" class="mb-5">
    <template #buttons>
      <BaseButton @click="changeSelectedTab('LearningResources')">Stored Resources</BaseButton>
      <BaseButton @click="changeSelectedTab('AddResources')">Add Resources</BaseButton>
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
      resource.id = this.learningResources.length;
      this.learningResources.push(resource);
    },
  },
};
</script>
