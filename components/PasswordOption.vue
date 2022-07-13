<template>
  <div>
    <div class="mt-10 max-w-lg mx-auto text-center">
      <p class="text-gray-100 text-2xl">
        {{ option.title }}
      </p>
    </div>
    <div class="mt-5 flex justify-center">
      <div
        v-for="(buttonValue, index) in option.buttons"
        :key="index"
        class="mx-5 cursor-pointer block p-3 rounded-lg"
        :class="
          options[option.category] === buttonValue
            ? 'bg-gray-100'
            : 'border border-gray-200'
        "
        @click="changeOptionValue(option.category, buttonValue)"
      >
        <span
          class="text-lg font-medium mx-10"
          :class="
            options[option.category] === buttonValue
              ? 'text-gray-900'
              : 'text-gray-100'
          "
        >
          {{ getButtonLabel(buttonValue) }}
        </span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { PasswordLength } from '~~/enums/enums';

interface PasswordOptionProps {
  option: {
    title: string;
    category: string;
    buttons: PasswordLength[] | boolean[];
  };
  options: {
    passwordLength: PasswordLength;
    includeSymbols: boolean;
    includeNumbers: boolean;
    includeUppercase: boolean;
  };
}
const props = defineProps<PasswordOptionProps>();

const getButtonLabel = (label: string | boolean) => {
  if (typeof label === 'boolean') {
    return label ? 'Sim' : 'Não';
  }
  return label;
};

const changeOptionValue = (optionName, value) => {
  props.options[optionName] = value;
};

const changePasswordLength = (length: PasswordLength) => {
  props.options.passwordLength = length;
};
</script>
