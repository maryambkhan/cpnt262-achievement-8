<template>
  <div>
    <img
      :src="blok.image.filename"
      class="
        mt-10
        m-auto
        flex
        justify-center
        h-60
        box-border
        hover:box-content
        border-2 border-black
        
      "
    />
    <p class="flex justify-center font-semibold">Id: {{ blok.id }}</p>
    <h1 class="flex justify-center font-bold text-2xl text-orange-700">
      {{ blok.name }}
    </h1>
    <p class="flex justify-center font-bold">
      <strong>Writer:</strong> &emsp; {{ blok.writer }}
    </p>
    <p class="flex justify-center font-bold">
      <strong>Director: </strong>&emsp; {{ blok.director }}
    </p>
    <p class="flex justify-center font-bold">
      <strong>Released on:</strong> &emsp;{{ blok.release_year }}
    </p>
  </div>
</template>

<script setup>
const props = defineProps({
  blok: {
    type: Object,
  },
});
console.log(`Movies content ${props.blok}`);
</script>
