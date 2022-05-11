<template>
    <Title>{{ title }} </Title>
    <div class="min-h-screen text-gray-900 ">
        <nav class="bg-white shadow text-lg p-6">
            <div class="container mx-auto flex items-center justify-between px-6">
                <div>
                    <NuxtLink to="/" ><img class="w-32" src="ng-logo.png" alt=""></NuxtLink>
                </div>
                <div>
                    <ul class="flex space-x-12">
                        <li><NuxtLink to="/om-oss">Om oss</NuxtLink></li>
                        <li><NuxtLink to="/baerekraft">Bærekraft</NuxtLink></li>
                        <li><NuxtLink to="/kontakt">Kontakt</NuxtLink></li>
                        <li><NuxtLink to="/posts">Artikler</NuxtLink></li>
                    </ul>
                </div>
            </div>
        </nav>
        <div class="container mx-auto p-6">
            <slot />
        </div>
    </div>
</template>

<style scoped>
nav ul li {
    @apply hover:text-orange-600 transition-colors ;
}
.router-link-active { 
    @apply text-stone-700 font-bold;
}
</style>

<script setup>
    const title = useState('title', () => "Norsk Gjenvinning")
</script>