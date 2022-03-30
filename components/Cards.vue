<template>
  <div class="
    place-items-center
      w-52
      md:56
      lg:w-64
      bg-blue-200
      shadow-lg shadow-blue-300
      m-auto
      mt-6
      p-8
      rounded-3xl">
    <img :src=blok.image.filename class="flex justify-center m-auto " />
     <h1 class="flex justify-center font-bold text-2xl">
      {{blok.title}}
    </h1>
    <p class="flex justify-center font-semibold">{{blok.sub_title}}</p>
    <p class="flex justify-center font-bold">{{blok.price}}</p>
    <img :src=blok.rating/>
  </div>
</template>

<script setup>
const props = defineProps({
  blok: {
    type: Object,
  },
});
console.log(`Cards content ${props.blok}`);
</script>
