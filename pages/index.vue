<template>
<header>
  <h1>
    {{ state.story.name }}
  </h1>
  <p>{{ state.story.created_at }}</p>
</header>
 <section>
    <h2>Components</h2>
  <Movies :blok="components[0]" />
  
  </section>
  <div>
    <pre>
      {{ pageContent }}
    </pre>
  </div>
</template>

<script setup>
// access the storyblok build in function
const storyapi = useStoryApi();
// Fetch the data
const { data: movies } = await storyapi.get("cdn/stories/movies-list/movies", {
  version: "draft",
});
// Make the data reactive
const state = reactive({ story: movies.story });

// Making it faster to get info from the content
const pageContent = state.story.content;

// Make it easy to assign content from components
const components = state.story.content.movie;
const pageInfo = {
  title: pageContent.name,
  description: state.story.content.description,
};
console.log(components);
</script>


