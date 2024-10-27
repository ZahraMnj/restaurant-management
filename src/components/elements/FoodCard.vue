<script setup>
import foods from "./foodInfo.js"

function resolveImagePath(imagePath) {
    return new URL(imagePath, import.meta.url).href;
}

</script>

<template>
    <ul class="grid grid-cols-6 h-fit ">
        <li v-for="food in foods" :key="food.id" class=" overflow-hidden h-52 rounded-lg align-top bg-white m-1 shadow-md  cursor-pointer">
            <img :src="resolveImagePath(food.image)" class="h-32 object-cover rounded-t-lg mb-4 shadow"/>
            <div class="mx-2 mb-4 text-sm ">
                <p class="font-medium">{{ food.name }} </p>
                <p class="text-red-900 text-xs my-2 "> {{ food.price }} تومان </p>
            </div>
        </li>
    </ul>
</template>