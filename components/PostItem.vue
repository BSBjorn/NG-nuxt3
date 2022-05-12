<template>
    <article class="relative flex flex-col justify-between group bg-white hover:shadow-xl transition-shadow duration-500">
        <NuxtLink :to="`/posts/${props.post.id}`">
        <div>
            <figure class="aspect-[4/3] overflow-hidden mb-8">
                <img class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-inherit" :src="`/images/image-${props.post.id}.jpg`" alt="">
            </figure>
        </div>
        <div class="p-4">
            <h1 class="text-lg text-stone-600 lg:text-2xl font-bold line-clamp-1 lg:line-clamp-2">{{ props.post.title }}</h1>
            <Button :class="'mt-4'" :url="`/posts/${props.post.id}`" :title="'Les mer'" />
        </div>
    </NuxtLink>
    </article>
</template>


<script setup>
const props = defineProps({
    post: Object,
})

</script>