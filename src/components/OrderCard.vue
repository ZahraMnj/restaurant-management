<script setup>
import { ref } from 'vue';
import { Icon } from '@iconify/vue';
import OrderButton from './elements/OrderButton.vue';
import ACalculator from './elements/ACalculator.vue';
import BCalculator from './elements/BCalculator.vue';

const OrderButtonOptions = ref([
    { title: 'یادداشت مشتری', icon: 'tabler:note' },
    { title: 'اطلاعات', icon: 'tabler:info-circle' },
    { title: 'مشتری', icon: 'tabler:user' },
    { title: 'لیست قیمت ها', icon: 'tabler:list' },
    { title: 'استرداد', icon: 'tabler:receipt-refund' },
    { title: 'تخفیف', icon: 'tabler:tag' },
    { title: 'کد', icon: 'tabler:barcode' },
    { title: 'بازنشانی برنامه ها', icon: 'tabler:star' },
    { title: 'انعام', icon: 'tabler:star' },
    { title: 'یادداشت داخلی', icon: 'tabler:tag' },
    { title: 'صورت حساب', icon: 'tabler:receipt' },
    { title: 'تقسیم', icon: 'tabler:box-multiple' },
    { title: 'مهمانان', icon: 'tabler:square-rounded-number-1' },
    { title: 'انتقال', icon: 'tabler:arrow-narrow-left' },
])

</script>


<template>
    <div class="h-screen overflow-hidden mt-4 ml-2 p-1 rounded-lg shadow-md bg-slate-200">
        <div class="h-1/4 w-full bg-white text-slate-600 flex flex-col items-center justify-center text-center">
            <Icon icon="tabler:shopping-cart-filled" class="size-12" />
            <p class="mt-2">سبد سفارش خالی است</p>
        </div>

        <div class="bg-blue-500 text-white h-10 flex items-center justify-center m-auto">
            <p>شماره میز</p>
        </div>

        <div class="grid grid-cols-6 gap-1 mt-1">
            <OrderButton :options="OrderButtonOptions" />
        </div>

        <div class="grid grid-cols-2 gap-1 mt-1">
            
            <div class="">
                <div class="flex items-center justify-center my-2 bg-blue-500 text-white p-2 rounded">
                    <Icon icon="tabler:chevron-left" class="size-5 mt-1" />
                    <p>پرداخت</p>
                </div>

                <div class="h-48 w-full pb-10 bg-white text-slate-600 flex flex-col items-center justify-center text-center mt-2 mb-4">
                    <Icon icon="tabler:bowl-spoon" class="size-5"/>
                    <p>سفارش</p>
                </div>
            </div>
      
            <BCalculator />
      
        </div>

    </div>
</template>