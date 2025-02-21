<template>
  <li
    class="flex flex-col justify-between w-full rounded overflow-hidden shadow-lg bg-white hover:shadow-xl transition-shadow duration-300"
  >
    <div class="px-6 py-4">
      <h2 class="font-bold text-xl mb-2 text-gray-800">{{ item.title }}</h2>
      <p class="text-gray-700 text-base">
        {{ item.description }}
      </p>
    </div>
    <div class="px-6 pt-4 pb-6 flex flex-col sm:flex-row gap-3">
      <a :href="item.link" target="_blank">
        <BaseButton />
      </a>
      <BaseButton class="bg-red-500 hover:bg-red-700">Delete</BaseButton>
    </div>
  </li>
</template>

<script>
import BaseButton from "../UI/BaseButton.vue";

export default {
  components: {
    BaseButton,
  },
  props: ["item"],
};
</script>
