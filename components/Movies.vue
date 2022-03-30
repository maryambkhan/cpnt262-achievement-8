<template>
  <div>
    <img :src=blok.image.filename class="flex justify-center m-auto w-1/4 h-1/4 mt-4 " />
		<p class="flex justify-center font-semibold">Id: {{ blok.id}}</p>
		<h1 class="flex justify-center font-bold text-2xl text-orange-700">{{ blok.name}}</h1>
		<p class="flex justify-center font-bold"><strong>Writer:</strong> &emsp; {{ blok.writer }}</p>
    <p class="flex justify-center font-bold"><strong>Director: </strong>&emsp; {{ blok.director }}</p>
    <p class="flex justify-center font-bold"><strong>Released on:</strong> &emsp;{{ blok.release_year }}</p>
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
