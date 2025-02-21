<template>
  <div class="px-6 py-4">
    <h2 class="font-bold text-xl mb-2 text-gray-800"><slot></slot></h2>
    <p class="text-gray-700 text-base"><slot name="description"></slot></p>
  </div>
  <div class="px-6 pt-4 pb-6 flex flex-col sm:flex-row gap-3">
    <slot name="buttons"></slot>
  </div>
</template>

<script>
export default {};
</script>
