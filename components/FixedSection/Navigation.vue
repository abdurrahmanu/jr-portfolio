<template>
    <div 
    @click="$emit('emitClickedNavigation', clickedNavigation)"
    :class="[activeNavigation ? 'dark:text-white text-black' : 'text-[#7d7d7d]']"
    class="navigation">
        <span class="inline-block">{{ navigationIndex }}</span>
        <div class="line"
        :class="[activeNavigation ? 'w-[51px] dark:bg-white bg-black' : 'bg-gray-500 w-[30px]']">
        </div>
        <div class="inline-block">{{ navigationName }}</div>
    </div>
</template>

<script setup>
const { fixedSectionData } = allData()

const emit = defineEmits(['emitClickedNavigation'])
const props = defineProps({
    navigationName: String,
    navigationIndex: Number,
    activeNavigation: Boolean
})

const clickedNavigation = ref(fixedSectionData[props.navigationName].name)
</script>

<style scoped>
.navigation {
    @apply font-normal text-[10px] screen-xl:text-[13px] screen-3xl:text-[16px] hover:text-black dark:hover:text-white w-fit flex gap-2 items-center tracking-[1.04px]
}

.line {
    @apply inline-block transition-all duration-200 h-[2px] 
}

</style>