<template>
  <div
    class="flex bg-[#5655E2] justify-end items-center mx-auto max-w-sm h-10 px-3 py-6"
  >
    <template v-for="(item, idx) in items">
      <UChip v-if="shouldRenderChip(item)" color="red" class="ml-2">
        <UButton
          :icon="item.icon"
          class="bg-transparent text-white hover:bg-transparent p-0.5"
        />
      </UChip>

      <UButton
        v-else
        :key="idx"
        :icon="item.icon"
        class="bg-transparent text-white hover:bg-transparent p-0.5 ml-2"
      />
    </template>
  </div>
</template>
<script setup lang="ts">
const items = [
  {
    name: 'notifications',
    icon: 'i-heroicons-bell',
    count: 0,
    link: '/chats',
  },
  {
    name: 'messages',
    icon: 'i-heroicons-chat-bubble-oval-left',
    count: 3,
    link: 'alerts',
  },
  {
    name: 'logout',
    icon: 'i-heroicons-power',
    count: null,
    link: 'logout',
  },
];

const shouldRenderChip = (item: any) => {
  return (
    item.count !== null && item.count !== undefined && item.count !== false
  );
};
</script>
<style></style>
