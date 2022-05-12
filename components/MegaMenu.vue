<template>
    <div class="fixed inset-0 lg:w-[500px] bg-orange-600 lg:h-auto lg:mt-20 z-50 shadow">
        <button class="absolute top-6 right-6 text-white hover:text-stone-200 z-50" @click="open = !open">Lukk</button>
        <ul class="h-full flex flex-col space-y-4 items-center justify-center lg:items-start">
            <MenuItem v-for="item in menuItems" :key="index" :title="item.title" :url="item.url"
                :children="item.children" />
        </ul>
    </div>
</template>

<script setup>
const props = defineProps({
    open: Boolean,
})
const open = useState('open');


const menuItems = [
    {
        title: 'Om Oss',
        url: '/om-oss',
        children: [
            { title: 'Virksomheten', url: '#', children: [] },
            { title: 'Våre Selskaper', url: '#', children: [] },
            { title: 'Ledelsen', url: '#', children: [] },
            { title: 'Visjon og verdier', url: '#', children: [] },
            { title: 'Historie', url: '#', children: [] },
            { title: 'For våre leverandører', url: '#', children: [] },
            { title: 'Årsrapporter', url: '#', children: [] },
            { title: 'Om gjenvinningsindustrien', url: '#', children: [] },
        ]
    },
    {
        title: 'Bærekraft', url: '/baerekraft', children: [
            { title: 'Sirkulærøkonomi', url: '#', children: [] },
            { title: 'Avfall er en global ressurs', url: '#', children: [] },
            { title: 'Innovasjon', url: '#', children: [] },
            { title: 'Bærekraftrapport', url: '#', children: [] },
        ]
    },
    { title: 'Artikler', url: '/posts', children: []},
    { title: 'Compliance', url: '#', children:[]},
    { title: 'Karriere', url: '#', children:[]},
    { title: 'Investor', url: '#', children:[]},
    { title: 'Presserom', url: '#', children:[]},
    { title: 'Varsling', url: '#', children:[]},
    { title: 'Kontakt', url: '#', children:[]},
]


</script>