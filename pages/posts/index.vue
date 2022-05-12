<template>
 <div class="py-4 lg:py-16 mx-4 md:mx-0">
      <h1 class="mb-2 lg:mb-8 text-center">Våre artikler</h1>
      <div class="grid md:grid-cols-2 gap-4 lg:gap-16">
        <PostItem v-for="post in mutatePosts()" :key="post.id" :post="post"/>
      </div>
    </div>
</template>

<script setup>
const { data: posts } = await useFetch('https://jsonplaceholder.typicode.com/posts')
function mutatePosts() {
  const computedPosts = Object.values(posts.value).slice(2,10);
  return computedPosts
}

onMounted( () => {
  mutatePosts()
})
</script>