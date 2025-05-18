<script setup>
import { ref } from 'vue';

const props = defineProps({
  comments: Array,
});

const emit = defineEmits(['submit']);

const tempComment = ref('');

const onSubmit = () => {
  emit('submit', tempComment.value);
  tempComment.value = '';
};
</script>

<template>
  <div class="p-4 flex flex-col gap-4 justify-center items-center">
    <input
      v-model="tempComment"
      placeholder="Write a comment"
      class="border p-2 rounded"
    />
    <button
      @click="onSubmit"
      class="ml-2 bg-blue-500 text-white px-3 py-1 rounded"
    >
      Submit
    </button>

    <ul class="mt-4 space-y-2">
      <li
        v-for="(c, index) in comments"
        :key="index"
        class="border p-2 rounded"
      >
        <strong>{{ c.time }}</strong
        >: {{ c.text }}
      </li>
    </ul>
  </div>
</template>

<style scoped></style>
