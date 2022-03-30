<template>
<header>
  <h1 class="flex justify-center font-bold text-2xl text-orange-900 bg-red-100 mx-auto px-4">
    {{ state.story.name }}
  </h1>
</header>
<!--StoryBlok -->
 <section>
   <h1 class="flex justify-center font-bold text-orange-900 text-2xl mt-4">StoryBlok Api</h1>
  <Movies :blok="components[0]" />
 <Movies :blok="components[1]" />
  
  <!--
  <div>
    <pre>
      {{ pageContent }}
    </pre>
  </div>
 -->
 </section>

 <!--Ghibli Api-->
     <section>
       <h1 class="flex justify-center font-bold text-orange-900 text-2xl mt-4">Ghibli Studio Api</h1>
       <div class="flex justify-center  mt-4">
      <ul class="marker:text-red-900 list-disc ">
        <li v-for="films in films" :key="films.id">
          {{ films.title }} &emsp; {{films.original_title}}
        </li>
      </ul>
       </div>
    <!--
      <pre>
    <h1>{{films}}</h1>
    </pre>
   -->
    </section>
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

//Ghibli Api
const {data: films} = await useAsyncData("films", ()=> 
$fetch("https://ghibliapi.herokuapp.com/films/"),
);
console.log(components);
</script>

