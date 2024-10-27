<script setup>
import HeaderLayout from './components/HeaderLayout.vue';
import MainBar from './components/MainBar.vue';
import FoodPage from './components/FoodPage.vue';
import OrderCard from './components/OrderCard.vue';

</script>

<template>
    <main class="min-h-screen mx-auto px-4 lg:px-8">
        <div class="overflow-hidden px-px pb-px">
            <HeaderLayout />

            <div class="h-[2px] w-full bg-gray-200 dark:bg-gray-800"></div>

            <div class="grid grid-cols-5">                
                <div class="col-span-3">
                    <MainBar />
                    <FoodPage />
                </div>

                <div class="col-span-2">
                    <OrderCard />  
                </div>

            </div>

        </div>
    </main>

</template>
