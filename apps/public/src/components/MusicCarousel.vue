<template>
    <TabGroup :selected-index="selectedIndex" @change="selectedIndex = $event">

        <TabList class="flex justify-center mt-4 space-x-2">
            <Tab v-for="(song, idx) in songs" :key="idx" class="w-3 h-3 rounded-full cursor-pointer" :class="{
                'bg-blue-500': selectedIndex === idx,
                'bg-gray-300': selectedIndex !== idx
            }">
                <span class="sr-only">{{ song.title }}</span>
            </Tab>
        </TabList>

        <TabPanel v-for="(song, idx) in songs" :key="idx"
            class="bg-white rounded-lg shadow-md p-6 flex flex-col items-center space-y-4 mt-6">
            <img :src="song.cover" alt="cover" class="w-48 h-48 rounded-md object-cover" />
            <h3 class="text-xl font-semibold">{{ song.title }}</h3>
            <div class="flex gap-4">
                <a v-for="(platform, pidx) in song.platforms" :key="pidx" :href="platform.url" target="_blank"
                    rel="noopener noreferrer" class="btn btn-sm btn-primary">
                    {{ platform.name }}
                </a>
            </div>
        </TabPanel>

    </TabGroup>
</template>

<script setup>
import { ref } from 'vue'
import { TabGroup, TabList, TabPanel, Tab } from '@headlessui/vue'

const songs = ref([
    {
        cover: '/justinlanImage1.jpeg',
        title: 'Song One',
        platforms: [
            { name: 'Spotify', url: 'https://spotify.com' },
            { name: 'Apple Music', url: 'https://apple.com/music' }
        ]
    },
    {
        cover: 'https://via.placeholder.com/150',
        title: 'Song Two',
        platforms: [
            { name: 'Spotify', url: 'https://spotify.com' },
            { name: 'YouTube', url: 'https://youtube.com' }
        ]
    }
])

const selectedIndex = ref(0)
</script>
