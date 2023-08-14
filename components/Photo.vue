<template>
  <div v-if="pending">Loading...</div>
  <ul v-else class="flex flex-wrap gap-2">
    <li v-for="photo in photos" :key="photo.id">
      <img :src="photo.thumbnailUrl" :alt="photo.title" />
    </li>
  </ul>
</template>

<script setup lang="ts">
type Photo = {
  albumId: number;
  id: number;
  title: string;
  url: string;
  thumbnailUrl: string;
};
const props = defineProps({
  albumId: { type: Number, required: true },
});
// TODO: props.albumIdが変更しても発火しない
const { data: photos, pending } = useFetch<Photo[]>("https://jsonplaceholder.typicode.com/photos", {
  params: { albumId: props.albumId },
});
</script>
