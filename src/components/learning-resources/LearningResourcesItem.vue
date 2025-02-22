<template>
  <li class="w-full">
    <BaseCard>
      <template #default>{{ item.title }}</template>
      <template #description>{{ item.description }}</template>
      <template #buttons>
        <a :href="item.link" target="_blank">
          <BaseButton class="w-full" />
        </a>
        <BaseButton class="bg-red-500 hover:bg-red-700" @click="deleteResource(item.title)"
          >Delete</BaseButton
        >
      </template>
    </BaseCard>
  </li>
</template>

<script>
export default {
  inject: ["deleteResource"],
  props: ["item"],
};
</script>
