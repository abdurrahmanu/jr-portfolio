<template>
    <div class="project">
        <div class="img-container">
            <img class="img" src="/projectBackground.png" alt="">
        </div>
        <div class="about-project">
            <div class="heading">{{ project.title }}</div>
            <div class="info">{{ project.info }}</div>
            <div class="flex justify-between pt-[2.74%]">
                <div class="btn">
                    <div>{{project.type }}</div>
                </div>
                <div @click="viewProjectLive" class="link">
                    <span>view <span class="md:inline hidden">project</span> </span>
                    <SvgComponentsArrowSvg/> 
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    index: Number,
    project: Object,
})

const viewProjectLive = () => {
    console.log(props.index)
}

</script>

<style scoped>
    .heading {
        @apply text-[14px] font-bold screen-xl:text-[32px] screen-md:text-[24px]
    }

    .link {
        @apply opacity-[0.6] flex gap-[7px] sm:gap-[17px] text-[10px] screen-lg:text-[16px] items-center font-normal
    }

    .about-project {
        @apply h-full px-[17.5px] relative flex flex-col
    }

    .img-container {
        @apply h-[62.7%] bg-black rounded-t-[17px] 
    }

    .img {
        @apply w-full max-h-[367px] relative
    }

    .project {
        @apply h-fit max-h-fit pb-[8.1%] gap-[5.8%] border-[rgba(255,255,255,0.10)]
        border-[1px] flex flex-col rounded-[17px] dark:bg-baseBlack bg-neutral-800 
    }

    .info {
        @apply text-zinc-400 dark:text-[#7D7D7D] pt-[2.74%] text-[10px] screen-lg:text-[16px] font-medium leading-[20.48px]
    }

    .btn {
        @apply bg-[rgba(240,219,79,0.10)] text-[10px] screen-lg:p-2 max-w-[500px] screen-lg:text-base font-normal text-[#F0DB4F] p-1 rounded-full w-fit
    }


    
</style>