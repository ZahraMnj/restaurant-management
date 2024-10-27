<script setup lang="ts">
import { Icon } from '@iconify/vue';

interface prop {
    options: [{
        title: string
        icon: string
    }]

}
const props = defineProps<prop>()
</script>

<template>
        <button v-for="(option, index) in options" :key="option.title"
        class="bg-white flex items-center justify-center gap-2 py-1 text-sm font-normal rounded-md col-span-2"
    :class="index >= options.length - 2 ? 'col-span-3' : ''">
            <Icon :icon="option.icon" class="size-5 mt-1" />
            <p>{{ option.title }}</p>
        </button>
</template>