<template>
    <div class="style">
        <div @click="useDirection">{{ scrollerDirection() }}</div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const emit = defineEmits([''])
const scrollPosition = ref(window.scrollY)
const windowHeight = ref(window.innerHeight)

window.addEventListener('scroll', event => {
    scrollPosition.value = window.scrollY
    emit('scrollerDirection', scrollerDirection())
})

window.addEventListener('resize', event => {
    windowHeight.value = window.innerHeight
    emit('scrollerDirection', scrollerDirection())
})

const scrollerDirection = () => {
    const halfScreenHeight = Math.floor(windowHeight.value / 2)
    if (halfScreenHeight < scrollPosition.value) return 'top'
    return 'bottom'
}

const useDirection = () => {
    if (scrollerDirection() === 'top') {
        
    }

    else if (scrollerDirection() === 'bottom') {

    }
}

</script>

<style scoped>
.style {
    @apply mb-2 w-fit p-[2px] fixed bottom-0 shadow shadow-black left-[50%] translate-x-[-50%] rounded-full bg-white z-[999999999] text-black font-mono font-bold text-[12px]
}

</style>