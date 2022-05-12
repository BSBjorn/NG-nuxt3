<template>
  <div class="">
    <div class="relative">
      <figure class="aspect-[16/6]">
        <img class="w-full h-full object-cover" src="/images/header-1.jpg" alt="">
      </figure>
      <div class="md:absolute bottom-0 p-4 lg:px-16 bg-stone-600/80 w-full text-white">
        <h2 class="text-xl lg:text-5xl mb-2 lg:mb-6">Drømmer om flere roboter og mer kunstig intelligens</h2>
        <p class="lg:text-xl">Tiril Bratt og Ove R. Gundersen jobber sammen for å perfeksjonere Norges smarteste industribedrift.</p>
        <Button :class="'mt-2'" url="#" title="Les mer" />
      </div>
    </div>
    <div class="py-4 lg:py-16 mx-4 md:mx-0">
      <div class="grid md:grid-cols-2 gap-4 lg:gap-16">
        <PostItem v-for="post in mutatePosts()" :key="post.id" :post="post"/>
      </div>
    </div>

  </div>

</template>

<script setup>
const { data: posts } = await useFetch('https://jsonplaceholder.typicode.com/posts')

function mutatePosts() {
  const computedPosts = Object.values(posts.value).slice(0,4);
  return computedPosts
}

onMounted( () => {
  mutatePosts()
})
</script>