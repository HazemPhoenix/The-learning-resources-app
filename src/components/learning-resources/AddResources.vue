<template>
  <form
    class="flex flex-col gap-3 w-full sm:w-4/12 mx-auto mt-5 border-1 border-gray-200 rounded-lg p-5"
  >
    <div class="flex flex-col gap-2">
      <label for="title" class="text-lg">Title</label>
      <input
        ref="title"
        type="text"
        class="focus:outline-blue-500 transition-all transition-100 p-2 outline-1 outline-gray-200"
      />
    </div>
    <div class="flex flex-col gap-2">
      <label for="description" class="text-lg">Description</label>
      <input
        ref="desc"
        type="text"
        class="focus:outline-blue-500 transition-all transition-100 p-2 outline-1 outline-gray-200"
      />
    </div>
    <div class="flex flex-col gap-2">
      <label for="description" class="text-lg">Link</label>
      <input
        ref="link"
        type="text"
        class="focus:outline-blue-500 transition-all transition-100 p-2 outline-1 outline-gray-200"
      />
    </div>
    <BaseButton type="submit" @click.prevent="submitHandler">Add</BaseButton>
  </form>
</template>

<script>
import BaseButton from "../UI/BaseButton.vue";

export default {
  components: {
    BaseButton,
  },
  inject: ["addResource"],
  methods: {
    submitHandler() {
      const res = {
        title: this.$refs.title.value,
        description: this.$refs.desc.value,
        link: this.$refs.link.value,
      };
      this.addResource(res);
    },
  },
};
</script>
