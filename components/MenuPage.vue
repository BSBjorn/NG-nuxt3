<template>
<div class="absolute inset-0 bg-orange-500 h-full flex flex-col space-y-4 items-center justify-center z-40 lg:ml-8 lg:shadow">
    <button><IconsArrowBack  class="w-8 mb-8 fill-white" /></button>
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
    menuItems: Array
})
</script>