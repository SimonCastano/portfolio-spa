<template>
    <section class="flex items-center px-44 py-6 justify-between ">
        <div :class="background"
            class="h-24 w-24 rounded-full border-double border-8">
        </div>
        <p class="text-xl font-extrabold text-gray-800 mx-1">
            <slot></slot>
        </p>
    </section>
</template>
<script setup>
defineProps({
    background: {
        type: String,
        default: "white",
    },
});
</script>
