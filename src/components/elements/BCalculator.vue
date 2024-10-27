<script setup>
import { ref } from 'vue';
import { Icon } from '@iconify/vue';

const display = ref('0');
const currentOperation = ref(null);
const previousValue = ref(null);
const shouldResetDisplay = ref(false);

const updateDisplay = (value) => {
  if (shouldResetDisplay.value) {
    display.value = value;
    shouldResetDisplay.value = false;
  } else {
    display.value = display.value === '0' ? value : display.value + value;
  }
};

const handleNumber = (num) => {
  updateDisplay(num);
};

const handleOperation = (op) => {
  if (currentOperation.value !== null) {
    calculate();
  }
  previousValue.value = parseFloat(display.value);
  currentOperation.value = op;
  shouldResetDisplay.value = true;
};

const calculate = () => {
  if (currentOperation.value === null || previousValue.value === null) return;
  const current = parseFloat(display.value);
  let result;
  switch (currentOperation.value) {
    case '+':
      result = previousValue.value + current;
      break;
    case '-':
      result = previousValue.value - current;
      break;
    case '*':
      result = previousValue.value * current;
      break;
    case '/':
      result = previousValue.value / current;
      break;
    default:
      return;
  }
  display.value = result.toString();
  currentOperation.value = null;
};

const clear = () => {
  display.value = '0';
  currentOperation.value = null;
  previousValue.value = null;
  shouldResetDisplay.value = false;
};

const toggleSign = () => {
  display.value = (parseFloat(display.value) * -1).toString();
};

const addDecimal = () => {
  if (!display.value.includes('.')) {
    display.value += '.';
  }
};
</script>

<template>
  <div class="bg-gray-100 p-4 rounded-lg shadow-md">
    <!-- <div class="bg-white p-2 mb-4 text-right text-2xl font-bold rounded">
      {{ display }}
    </div> -->
    <div class="grid grid-cols-4 gap-2 font-medium text-xs">
      <button
        v-for="(item, index) in ['1', '2', '3', 'تعداد', '4', '5', '6', '% تخفیف', '7', '8', '9', 'قیمت', '+/-', '0', '.', '']"
        :key="index"
        class="bg-white size-[52px] flex items-center justify-center rounded shadow hover:bg-gray-100 transition-colors"
        @click="() => {
          if (item === 'تعداد') handleOperation('*');
          else if (item === '% تخفیف') handleOperation('-');
          else if (item === 'قیمت') handleOperation('+');
          else if (item === '+/-') toggleSign();
          else if (item === '.') addDecimal();
          else if (item === '') clear();
          else handleNumber(item);
        }"
      >
        <template v-if="item === ''">
          <Icon icon="tabler:label" class="size-5" />
        </template>
        <template v-else>
          {{ item }}
        </template>
      </button>
    </div>
  </div>
</template>