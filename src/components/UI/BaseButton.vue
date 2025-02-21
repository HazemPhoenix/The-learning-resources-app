<template>
  <button
    :type="type"
    :class="[
      'inline-block hover:bg-blue-950 text-white font-bold py-2 px-4 rounded-full transition-colors duration-300 hover:cursor-pointer',
      color,
    ]"
  >
    <slot>Visit</slot>
  </button>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      required: false,
      default: "button",
    },
    color: {
      type: String,
      required: false,
      default: "bg-blue-800",
    },
  },
};
</script>
