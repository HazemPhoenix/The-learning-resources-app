<template>
  <div
    class="flex flex-col justify-between w-full rounded-lg shadow-lg bg-white hover:shadow-xl transition-shadow duration-300"
  >
    <div class="px-6 py-4" v-if="$slots.default || $slots.description">
      <h2 v-if="$slots.default" class="font-bold text-xl mb-2 text-gray-800"><slot></slot></h2>
      <p v-if="$slots.description" class="text-gray-700 text-base">
        <slot name="description"></slot>
      </p>
    </div>
    <div
      v-if="$slots.buttons"
      :class="['px-6 pt-4 pb-6 flex flex-col sm:flex-row gap-3', buttonAlignment]"
    >
      <slot name="buttons"></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    alignButtons: {
      type: String,
      default: "start",
    },
  },
  computed: {
    buttonAlignment() {
      let alignment;
      switch (this.alignButtons) {
        case "start":
          alignment = "justify-start";
          break;
        case "center":
          alignment = "justify-center";
          break;
        case "end":
          alignment = "justify-end";
          break;
      }
      return alignment;
    },
  },
};
</script>
