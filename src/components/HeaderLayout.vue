<script setup>
import {Icon} from "@iconify/vue";
import AButton from "./elements/AButton.vue";

</script>

<template> 
<div>
  <div class="" >
    <div class="grid grid-cols-5 items-center">

      <div class="flex items-center justify-start gap-4">
        <Icon icon="tabler:menu-2" />
        <Icon icon="tabler:wifi" class="text-green-700"/>
        <p class="font-medium text-sm">ادمین</p>
      </div>

      <div></div>

      <div class="flex items-center justify-end mb-1">
        <AButton >بازگشت 
        <Icon icon="tabler:chevron-left" class="mt-1 size-6 -mr-1"/></AButton>
      </div>

      <div></div>

      <div class=" flex items-center justify-end grid-cols-2">
        <button type="button" @click="$emit('update:toggle' , !isDark)"
                class="rounded-lg bg-slate-100 p-1.5 text-slate-500 hover:text-slate-400 sm:bg-transparent">
          <Icon icon="tabler:moon" class="size-6" v-if="isDark"/>
          <Icon icon="tabler:sun" class="size-6" v-else/>
        </button>
       <img src="../assets/images/logo4.png" alt="" class="w-28">
      </div>

    </div>
  </div>

</div>
</template>
