<template>
  <li
    class="flex flex-col justify-between w-full rounded overflow-hidden shadow-lg bg-white hover:shadow-xl transition-shadow duration-300"
  >
    <BaseCard>
      <template #default>{{ item.title }}</template>
      <template #description>{{ item.description }}</template>
      <template #buttons>
        <a :href="item.link" target="_blank">
          <BaseButton class="w-full" />
        </a>
        <BaseButton class="bg-red-500 hover:bg-red-700">Delete</BaseButton>
      </template>
    </BaseCard>
  </li>
</template>

<script>
import BaseButton from "../UI/BaseButton.vue";
import BaseCard from "../UI/BaseCard.vue";

export default {
  components: {
    BaseButton,
    BaseCard,
  },
  props: ["item"],
};
</script>
