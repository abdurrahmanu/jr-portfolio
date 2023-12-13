<template>
    <div class="nav">
        <div :class="[openMenu ? 'h-10 bg-black' : 'h-fit']" class="flex rounded-full relative justify-between items-center w-full">
            <div :class="[openMenu ? 'w-[20%] rounded-r-none' : '']" class="flex pl-3 gap-2 items-center p-2 bg-black rounded-full px-2">
                <div @click="toggle" class="w-2 h-2 rounded-full bg-white dark:bg-white"></div>
                <div class="text-[9px]">J.A FOLIO</div>
            </div>
            <div ref="menuElement" @click="openMenu = !openMenu" :class="[openMenu ? 'w-[80%] rounded-l-none' : 'w-fit']" class="bg-black text-gray-500 text-[8px] sm:text-[14px] uppercase rounded-full p-2">
                <div v-if="openMenu" class="flex absolute left-[50%] top-[50%] w-[80%] translate-y-[-50%] translate-x-[-50%] justify-evenly items-center transition-all duration-500">
                    <div class="hover:text-white hover:animate-pulse">About Me</div>
                    <div class="hover:text-white hover:animate-pulse">My Skills</div>
                    <div class="hover:text-white hover:animate-pulse">My Projects</div>
                    <div class="hover:text-white hover:animate-pulse">Contact Me</div>
                </div>
                <div v-else class="h-[2px] border-y border-white py-[3px] w-[15px]"></div>
                <div v-if="openMenu" class="font-mono absolute right-3 text-[14px] text-red-300 top-[50%] translate-y-[-50%]">X</div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const openMenu = ref(false);
const menuElement = ref(null)
const darkmodeStore = useDarkMode()
const navigations = ['About Me', 'My Skills', 'My Projects', 'Contact Me']

const toggle = () => {
    darkmodeStore.darkMode = !darkmodeStore.darkMode
    localStorage.setItem('portfolioBgMode', darkmodeStore.darkMode)
}

onBeforeMount(() => {
    darkmodeStore.checkLocalStorageForSavedBackground()
})
</script>

<style scoped>
.nav {
    @apply w-full sm:sticky max-w-[1228px] m-auto fixed top-0 left-0 px-6 h-[75px] short-screen:h-[110px] sm:h-[110px] md:h-[160px] text-[10px] flex justify-around items-center z-[999999999]
}
</style>