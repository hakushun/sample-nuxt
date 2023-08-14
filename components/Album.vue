<template>
  <div class="flex flex-col gap-8">
    <ul class="h-80 overflow-y-scroll">
      <li v-for="album in albums" :key="album.id">
        <button type="button" @click="handleClick(album.id)">{{ album.title }}</button>
      </li>
    </ul>
    <template v-if="albumId">
      <Photo :album-id="albumId" />
    </template>
  </div>
</template>

<script setup lang="ts">
type Album = {
  userId: number;
  id: number;
  title: string;
};
const albumId = useState<number | null>("albumId", () => null);
const { data: albums } = await useFetch<Album[]>("https://jsonplaceholder.typicode.com/albums");

const handleClick = (id: number) => {
  albumId.value = id;
};
</script>
