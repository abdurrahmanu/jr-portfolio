<template>
    <div :class="[darkMode.toggleDarkMode]">
        <Home />
    </div>
</template>

<script setup>
const darkMode = useDarkMode()
</script>




