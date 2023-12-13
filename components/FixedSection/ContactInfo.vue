<template>
    <div @click="goToLink" class="flex font-medium gap-[10px] dark:text-slate-300 text-black">
        <component class="p-1 rounded-full bg-black" :is="svg[0]" />
        <div class="flex items-center text-[12px] ">{{ name }}</div>
    </div>
</template>

<script setup>
const {socialLinks } = allData()

const props = defineProps({
    name: String,
    link: String,
    svg: Array
})

const goToLink = () => {
    console.log(props.link)
    // window.go(`${socialLinks[props.contact]}`, '_blank')
}

</script>
