<template>
<div class="absolute inset-0 bg-orange-500 h-full flex flex-col space-y-4 items-center lg:items-start justify-center z-40 lg:ml-8 lg:shadow">
    <button><IconsArrowBack  class="w-8 mb-2 lg:ml-8 fill-white hover:text-teal-300 hover:-translate-x-2 transition" /></button>
    <h2 class="text-stone-100 w-full lg:pl-8 text-xl border-b-2 border-stone-100">{{props.parent}}</h2>
    <MenuItem v-for="item in props.menuItems" 
        :key="index" 
        :title="item.title" 
        :url="item.url" 
        :children="item.children"
    />
</div>
</template>

<script setup>
const props = defineProps({
    menuItems: Array,
    parent: String
})
</script>