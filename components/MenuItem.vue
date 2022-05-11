<template>
    <li class="inline-flex items-center pl-8">
        <NuxtLink :to="props.url" @click="open = !open">{{props.title}}</NuxtLink>
        <span v-if="props.children.length > 0" @click="pageOpen = !pageOpen" >
            <IconsArrowBack :class="'rotate-180 w-6 ml-4 fill-white'"/>
            <Transition>
                <MenuPage v-if="pageOpen" :menuItems="props.children"/> 
            </Transition>
        </span>  
    </li>
</template>

<style scoped>
nav ul li a {
    @apply text-white hover:text-teal-300 transition-colors font-heading text-3xl ;
}
</style>

<script setup>
const props = defineProps({
    title:  String,
    url:  String,
    children: Array
})
const open = useState('open');

const pageOpen = ref(false)

</script>