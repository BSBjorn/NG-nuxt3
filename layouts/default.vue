<template>
    <Title>{{ title }} </Title>
    <div class="min-h-screen text-gray-900 bg-stone-200">
        <nav class="bg-white shadow text-lg ">
            <div class="container mx-auto flex flex-wrap items-center justify-between h-20">
                <div>
                    <NuxtLink to="/" ><img class="w-32" src="ng-logo.png" alt=""></NuxtLink>
                </div>
                <div>
                    <button class="relative z-50" @click="open = !open" >{{!open ? 'åpne' : 'lukk'}}</button>
                    <Transition>
                        <MegaMenu v-if="open" />
                    </Transition>
                </div>
            </div>
        </nav>
        <div class="container mx-auto">
            <slot />
        </div>
    </div>
</template>

<style>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.2s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

</style>

<script setup>
    const title = useState('title', () => "Norsk Gjenvinning")
    const open = useState('open', false)
</script>