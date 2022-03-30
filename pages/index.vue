<template>
<header>
  <h1 class="flex justify-center font-bold text-2xl text-orange-700">
    {{ state.story.name }}
  </h1>
</header>
 <section>
  <Cards :blok="components" />
  </section>
  <!--
  <div>
    <pre>
      {{ pageContent }}
    </pre>
  </div>
  -->
</template>

<script setup>
// access the storyblok build in function
const storyapi = useStoryApi();
// Fetch the data
const { data: cards } = await storyapi.get("cdn/stories/first-project/card-layout", {
  version: "draft",
});
// Make the data reactive
const state = reactive({ story: cards.story });

// Making it faster to get info from the content
const pageContent = state.story.content;

// Make it easy to assign content from components
const components = state.story.content;


const pageInfo = {
  title: pageContent,
  description: state.story.content.description,
};
console.log(components);
</script>


