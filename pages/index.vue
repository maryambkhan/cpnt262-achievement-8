<template>
<header>
  <h1 class="flex justify-center font-bold text-2xl text-orange-900 bg-red-100 mx-auto px-4">
    {{ state.story.name }}
  </h1>
</header>
 <section>
  <Movies :blok="components[0]" />
 <Movies :blok="components[1]" />
  </section>
  <!--
  <div>
    <pre>
      {{ pageContent }}
    </pre>
  </div>
 -->
 <TheFooter />
</template>

<script setup>

const storyapi = useStoryApi();

const { data: movie } = await storyapi.get("cdn/stories/movies-list/movies", {
  version: "draft",
});


const state = reactive({ story: movie.story });


const pageContent = state.story.content;


const components = state.story.content.movie;

const pageInfo = {
  title: pageContent,
  description: state.story.content.description,
};
console.log(components);
</script>

