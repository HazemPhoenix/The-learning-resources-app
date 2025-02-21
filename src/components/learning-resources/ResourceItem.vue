<template>
  <li
    class="flex flex-col justify-between w-full rounded overflow-hidden shadow-lg bg-white hover:shadow-xl transition-shadow duration-300"
  >
    <div class="px-6 py-4">
      <h2 class="font-bold text-xl mb-2 text-gray-800">{{ item.title }}</h2>
      <h3 class="text-gray-700 text-base">
        {{ item.description }}
      </h3>
    </div>
    <div class="px-6 pt-4 pb-6">
      <a
        :href="item.link"
        target="_blank"
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-6 rounded-full transition-colors duration-300"
      >
        Visit
      </a>
    </div>
  </li>
</template>

<script>
export default {
  props: ["item"],
};
</script>
