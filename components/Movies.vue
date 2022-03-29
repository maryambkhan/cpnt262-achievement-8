<template>
  <div>
    <h1>
        {{ blok.release_year }}
    </h1>
		<p>{{ blok._id}}</p>
		<p>{{ blok.name}}</p>
		<p>{{ blok.director }}</p>
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
