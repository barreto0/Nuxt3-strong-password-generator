<template>
  <div class="bg-gray-600 p-5 h-screen">
    <div class="max-w-screen-lg py-5 mx-auto bg-gray-700 rounded-xl">
      <div class="max-w-lg mx-auto text-center">
        <p class="text-4xl font-bold text-gray-100">
          Gerador de senha forte 🔒
        </p>
      </div>
      <PasswordOption
        v-for="option in optionsArray"
        :option="option"
        :options="options"
        @printOption="() => printOption(option.title)"
      />
      <div class="mt-10 max-w-lg mx-auto text-center">
        <button
          type="submit"
          class="w-40 px-5 py-3 text-sm font-medium text-white bg-gray-800 rounded-lg"
          @click="generatePassword"
        >
          Gerar senha
        </button>
      </div>

      <div class="mt-10 max-w-lg mx-auto text-center">
        <p class="text-gray-100 text-2xl">Sua senha gerada</p>
      </div>
      <!-- <ModalPasswordReadyModal /> -->
      <div class="mt-10 max-w-lg mx-auto text-center">
        <input
          class="w-full p-3 text-sm border-gray-200 rounded-lg"
          placeholder="Sua senha aparecerá aqui"
          type="text"
          id="name"
          v-model="generatedPassword"
        />
      </div>
    </div>
    <div class="text-center mt-3">
      <p class="text-gray-50">barreto 2022</p>
    </div>
  </div>
</template>

<script setup lang="ts">
import type { Ref } from 'vue';
import { PasswordLength } from '@/enums/enums';

const optionsArray = [
  {
    title: 'Escolha o tamanho da senha',
    category: 'passwordLength',
    buttons: [
      PasswordLength.SIXTEEN,
      PasswordLength.THIRTYTWO,
      PasswordLength.SIXTYFOUR,
    ],
  },
  {
    title: 'Incluir símbolos (!@#$%^&*) ',
    category: 'includeSymbols',
    buttons: [true, false],
  },
  {
    title: 'Incluir Números (0-9)',
    category: 'includeNumbers',
    buttons: [true, false],
  },
  {
    title: 'Incluir letras caixa alta (A-Z)',
    category: 'includeUppercase',
    buttons: [true, false],
  },
];

interface OptionsState {
  passwordLength: PasswordLength;
  includeSymbols: boolean;
  includeNumbers: boolean;
  includeUppercase: boolean;
}

const options: OptionsState = reactive({
  passwordLength: PasswordLength.SIXTYFOUR,
  includeSymbols: true,
  includeNumbers: true,
  includeUppercase: true,
});

const generatedPassword: Ref<string> = ref('');

const generatePassword = () => {
  console.log(options);
};

const printOption = (option: string) => {
  console.log(option);
};
</script>

<!-- const state = ref({
  isVisible: true,
  name: 'Markus',
});

// 1. You must use `.value` to access properties
//    of a `ref()` object. With `reactive()` you
//    could do `state.isVisible = false`.
state.value.isVisible = false;

// 2. You can swap the complete object. You can't
//    do that with `reactive()` objects!
state.value = {
  isVisible: false,
  name: 'John',
}; -->
