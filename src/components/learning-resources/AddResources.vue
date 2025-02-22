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
  <BaseDialog v-if="!isValidInputs" @close="closeDialog">
    <template #default>
      <p>Please fill in all of the input fields before adding the resource.</p>
    </template>
    <template #actions>
      <BaseButton @click="closeDialog">Close</BaseButton>
    </template>
  </BaseDialog>
</template>

<script>
import BaseButton from "../UI/BaseButton.vue";
import BaseDialog from "../UI/BaseDialog.vue";

export default {
  components: {
    BaseButton,
    BaseDialog,
  },
  inject: ["addResource"],
  data() {
    return {
      isValidInputs: true,
    };
  },
  methods: {
    submitHandler() {
      const title = this.$refs.title.value;
      const description = this.$refs.desc.value;
      const link = this.$refs.link.value;
      if (title.trim() === "" || description.trim() === "" || link.trim() === "") {
        this.isValidInputs = false;
        return;
      }

      const res = {
        title,
        description,
        link,
      };

      this.addResource(res);
      this.clearFields();
    },
    clearFields() {
      this.$refs.title.value = "";
      this.$refs.desc.value = "";
      this.$refs.link.value = "";
    },
    closeDialog() {
      this.isValidInputs = true;
    },
  },
};
</script>
