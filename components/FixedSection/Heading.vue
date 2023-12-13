<template>
    <h1
    v-motion
    :initial="{ opacity: 0.3}"
    :enter="{ opacity: 1, transition: { opacity: { duration: 1000} }}"
    class="typography-heading">
        <p>{{ fixedHeading[0] }}</p>
        <p>{{ fixedHeading[1] }}</p>
    </h1>
</template>

<script setup>
const props = defineProps({
    fixedHeading: Array
})
</script>

<style scoped>
    .typography-heading {
        @apply font-bold text-[30px] dark:text-[rgba(255,255,255,0.80)] text-zinc-900 short-screen:text-[40px]
        screen-2xl:text-custom-2xl screen-xl:text-custom-xl screen-lg:text-custom-lg screen-md:text-custom-md screen-sm:text-custom-sm screen-3xl:text-custom-3xl
    }
</style>