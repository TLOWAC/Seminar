<script setup lang="ts">
import { ref } from "vue";

const example1 = new Vue({
  data: {
    images: [
      "https://source.unsplash.com/collection/94734566/1920x1080",
      "https://source.unsplash.com/collection/94734566/1920x1080",
      "https://source.unsplash.com/collection/94734566/1920x1080",
    ],
  },
});

const images = ref(props.images);
</script>

<template>
  <div flex="~" w="min" border="~ gray-400 opacity-50 rounded-md">
    <ul id="example1">
      <li v-for="image in images">
        {{ image }}
      </li>
    </ul>
  </div>
</template>
