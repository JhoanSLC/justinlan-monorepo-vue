<template>
    <div class="relative min-h-screen text-black overflow-hidden">
        <div v-for="(url, index) in urls" :key="index"
            class="absolute inset-0 bg-no-repeat bg-cover bg-center transition-opacity duration-1000" :class="[
                index === counter ? 'opacity-60' : 'opacity-0'
            ]" :style="{ backgroundImage: `url('${url}')` }"></div>
        <div class="relative z-10">
            <slot />
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const urls = [
    '/justinImage1.jpeg',
    '/justinImage2.jpeg',
    '/justinImage3.jpeg',
    '/justinImage4.jpeg',
    '/justinImage5.jpeg'
];

const counter = ref(0);

onMounted(() => {
    setInterval(() => {
        counter.value = (counter.value + 1) % urls.length;
    }, 10000);
});
</script>
