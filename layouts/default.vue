<template>
  <Title>{{ title }} </Title>
  <div class="min-h-screen text-stone-800 bg-gradient-to-br from-stone-200 to-teal-50">
    <nav class="bg-white shadow text-lg px-4 z-50">
      <div class="container mx-auto flex flex-wrap items-center justify-between h-20">
        <div>
          <NuxtLink to="/"><img class="w-32 lg:w-48" src="/ng-logo.png" alt=""></NuxtLink>
        </div>
        <ul class="hidden lg:flex space-x-16 font-heading">
          <li class="hover:text-teal-700 transition-color">
            <NuxtLink :to="'/om-oss'" @click="open = false">Om oss</NuxtLink>
          </li>
          <li class="hover:text-teal-700 transition-color">
            <NuxtLink :to="'/baerekraft'" @click="open = false">Bærekraft</NuxtLink>
          </li>
          <li class="hover:text-teal-700 transition-color">
            <NuxtLink :to="'/posts'" @click="open = false">Artikler</NuxtLink>
          </li>
          <li class="hover:text-teal-700 transition-color">
            <NuxtLink :to="'/kontakt'" @click="open = false">Kontakt</NuxtLink>
          </li>
        </ul>
        <div>
          <button class="relative z-50" @click="open = !open">
            <div class="menuIcon">
              <div></div>
            </div>
          </button>
          <Transition>
            <MegaMenu v-if="open" />
          </Transition>
        </div>
      </div>
    </nav>
    <div class="container mx-auto z-40">
      <slot />
    </div>
    <footer class="p-4 bg-white shadow  dark:bg-stone-800 mt-16">
      <div class="container mx-auto md:flex md:items-center md:justify-between md:p-6">
        <span class="text-sm text-gray-500 sm:text-center dark:text-gray-400">© 2022 <a href="https://nggroup.no"
            class="hover:underline">Norsk Gjenvinning Norge AS</a>. Alle rettigheter.</span>
        <ul class="flex space-x-4 flex-wrap items-center mt-3 text-sm text-gray-500 dark:text-gray-400 sm:mt-0">
          <li>
            <NuxtLink :to="'/om-oss'" @click="open = false">Om oss</NuxtLink>
          </li>
          <li>
            <NuxtLink :to="'/baerekraft'" @click="open = false">Bærekraft</NuxtLink>
          </li>
          <li>
            <NuxtLink :to="'/posts'" @click="open = false">Artikler</NuxtLink>
          </li>
          <li>
            <NuxtLink :to="'/kontakt'" @click="open = false">Kontakt</NuxtLink>
          </li>
        </ul>
      </div>
    </footer>
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


.menuIcon {
  transform: translate(-100%, -60%);
  position: absolute;
  width: 30px;
}

.menuIcon:before,
.menuIcon:after,
.menuIcon div {
  @apply bg-stone-800 block h-1 rounded-sm my-1 mx-0 transition-all duration-300;
  content: "";
}

.menuIcon:hover:before {
  @apply translate-y-2 rotate-[135deg];
}

.menuIcon:hover:after {
  @apply -translate-y-2 -rotate-[135deg];
}

.menuIcon:hover div {
  @apply scale-0
}
</style>

<script setup>
  const title = useState('title', () => "Norsk Gjenvinning")
  const open = useState('open', false)
</script>