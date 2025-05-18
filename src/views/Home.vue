<script setup>
import { ref, reactive, computed } from 'vue';

import CommentsList from '../components/CommentsList.vue';

const msg = computed(() => (count.value > 5 ? 'Passed' : 'Failed'));
const count = ref(0);
const state = reactive({
  comments: [],
});

const onSubmit = (newComment) => {
  if (newComment.trim()) {
    state.comments.push({
      text: newComment,
      time: new Date().toLocaleTimeString(),
    });
  } else {
    window.alert('Please enter a comment.');
  }
};

const increment = () => {
  if (count.value < 10) count.value++;
  else return;
};
</script>

<template>
  <div class="pt-10 flex flex-col gap-10 justify-center items-center">
    <h1
      class="text-3xl font-bold"
      :class="count > 5 ? 'text-green-500' : 'text-red-500'"
    >
      {{ msg }}
    </h1>

    <p v-if="count === 10">FULL MARK</p>

    <p class="text-3xl">Mark is {{ count }}.</p>

    <button
      class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-5"
      @click="increment"
    >
      Click me to increment!
    </button>
  </div>

  <CommentsList :comments="state.comments" @submit="onSubmit" />
</template>

<style scoped></style>
