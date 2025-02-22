<template>
  <div>
    <div class="fixed inset-0 bg-black/50 backdrop-blur-sm z-40" @click="$emit('close')"></div>
    <dialog
      open
      class="fixed top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 rounded-xl shadow-2xl p-6 bg-white w-full max-w-lg border-none outline-none z-50"
    >
      <header class="border-b border-gray-200 pb-4 mb-4">
        <slot name="header">
          <h2 class="text-2xl font-bold text-gray-800">
            {{ title }}
          </h2>
        </slot>
      </header>

      <section class="mb-6 text-gray-600 leading-relaxed">
        <slot></slot>
      </section>

      <menu class="flex justify-end space-x-3">
        <slot name="actions"></slot>
      </menu>
    </dialog>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "Invalid inputs.",
    },
  },
  emits: ["close"],
};
</script>
