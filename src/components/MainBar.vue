<script setup>
import {Icon} from "@iconify/vue";

</script>

<template>
    <div class="flex items-center justify-between mt-4 ml-2 p-2 rounded-lg shadow-md bg-slate-200">
        <ul class="flex items-center justify-start gap-5 text-sm font-medium">
            <li><Icon icon="tabler:home-2" class="size-5"/></li>
            <Icon icon="tabler:caret-left-filled" class="flex items-center size-3 -ml-4 mt-1"/>
            <li>غذا</li>
            <li>دسر</li>
            <li>وعده اصلی</li>
            <li>منو پیشنهادی</li>
            <li>پیش غذا</li>
        </ul>
        
        <div class="flex items-center justify-end  rounded-md px-2.5 py-2 shadow-sm  transition text-sm border-gray-300 dark:border-gray-800 text-gray-900 dark:text-gray-50 placeholder-gray-400 dark:placeholder-gray-500 bg-white dark:bg-gray-950 focus:outline-none focus:ring-2 focus:ring-blue-200 focus:dark:ring-blue-700/30 focus:border-primary focus:dark:border-blue-700">
            <input type="text" placeholder="جستجوی محصولات..." class="relative block w-full appearance-none outline-none">
            <Icon icon="tabler:search" class="size-4"/>
        </div>

    </div>
</template>