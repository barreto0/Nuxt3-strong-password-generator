<template>
  <div class="bg-gray-600 p-5 h-screen">
    <div class="max-w-screen-lg py-5 mx-auto bg-gray-700 rounded-xl">
      <div class="max-w-lg mx-auto text-center">
        <p class="text-4xl font-bold text-gray-100">
          Gerador de senha forte 🔒
        </p>
      </div>
      <div class="mt-10 max-w-lg mx-auto text-center">
        <p class="text-gray-100 text-2xl">
          Escolha o tamanho da senha
        </p>
      </div>
      <div class="mt-5 flex justify-center">
        <div
          class="mx-5 cursor-pointer block p-3 rounded-lg"
          :class="
            options.passwordLength === PasswordLength.SIXTEEN
              ? 'bg-gray-100'
              : 'border border-gray-200'
          "
          @click="changePasswordLength(PasswordLength.SIXTEEN)"
        >
          <span
            class="text-lg font-medium mx-10"
            :class="
              options.passwordLength === PasswordLength.SIXTEEN
                ? 'text-gray-900'
                : 'text-gray-100'
            "
          >
            16
          </span>
        </div>

        <div
          class="mx-5 cursor-pointer block p-3 rounded-lg"
          :class="
            options.passwordLength === PasswordLength.THIRTYTWO
              ? 'bg-gray-100'
              : 'border border-gray-200'
          "
          @click="changePasswordLength(PasswordLength.THIRTYTWO)"
        >
          <span
            class="text-lg font-medium mx-10"
            :class="
              options.passwordLength === PasswordLength.THIRTYTWO
                ? 'text-gray-900'
                : 'text-gray-100'
            "
          >
            32
          </span>
        </div>

        <div
          class="mx-5 cursor-pointer block p-3 rounded-lg"
          :class="
            options.passwordLength === PasswordLength.SIXTYFOUR
              ? 'bg-gray-100'
              : 'border border-gray-200'
          "
          @click="changePasswordLength(PasswordLength.SIXTYFOUR)"
        >
          <span
            class="text-lg font-medium mx-10"
            :class="
              options.passwordLength === PasswordLength.SIXTYFOUR
                ? 'text-gray-900'
                : 'text-gray-100'
            "
          >
            64
          </span>
        </div>
      </div>

      <div class="mt-10 max-w-lg mx-auto text-center">
        <p class="text-gray-100 text-2xl">
          Incluir símbolos (!@#$%^&*)
        </p>
      </div>
      <div class="mt-5 flex justify-center">
        <div
          class="mx-5 cursor-pointer block p-3 rounded-lg"
          :class="
            options.includeSymbols
              ? 'bg-gray-100'
              : 'border border-gray-200'
          "
          @click="options.includeSymbols = true"
        >
          <span
            class="text-lg font-medium mx-10"
            :class="
              options.includeSymbols
                ? 'text-gray-900'
                : 'text-gray-100'
            "
          >
            Sim
          </span>
        </div>

        <div
          class="mx-5 cursor-pointer block p-3 rounded-lg"
          :class="
            !options.includeSymbols
              ? 'bg-gray-100'
              : 'border border-gray-200'
          "
          @click="options.includeSymbols = false"
        >
          <span
            class="text-lg font-medium mx-10"
            :class="
              !options.includeSymbols
                ? 'text-gray-900'
                : 'text-gray-100'
            "
          >
            Não
          </span>
        </div>
      </div>

      <div class="mt-10 max-w-lg mx-auto text-center">
        <p class="text-gray-100 text-2xl">Incluir Números (0-9)</p>
      </div>
      <div class="mt-5 flex justify-center">
        <div
          class="mx-5 cursor-pointer block p-3 rounded-lg"
          :class="
            options.includeNumbers
              ? 'bg-gray-100'
              : 'border border-gray-200'
          "
          @click="options.includeNumbers = true"
        >
          <span
            class="text-lg font-medium mx-10"
            :class="
              options.includeNumbers
                ? 'text-gray-900'
                : 'text-gray-100'
            "
          >
            Sim
          </span>
        </div>

        <div
          class="mx-5 cursor-pointer block p-3 rounded-lg"
          :class="
            !options.includeNumbers
              ? 'bg-gray-100'
              : 'border border-gray-200'
          "
          @click="options.includeNumbers = false"
        >
          <span
            class="text-lg font-medium mx-10"
            :class="
              !options.includeNumbers
                ? 'text-gray-900'
                : 'text-gray-100'
            "
          >
            Não
          </span>
        </div>
      </div>

      <div class="mt-10 max-w-lg mx-auto text-center">
        <p class="text-gray-100 text-2xl">
          Incluir letras caixa alta (A-Z)
        </p>
      </div>
      <div class="mt-5 flex justify-center">
        <div
          class="mx-5 cursor-pointer block p-3 rounded-lg"
          :class="
            options.includeUppercase
              ? 'bg-gray-100'
              : 'border border-gray-200'
          "
          @click="options.includeUppercase = true"
        >
          <span
            class="text-lg font-medium mx-10"
            :class="
              options.includeUppercase
                ? 'text-gray-900'
                : 'text-gray-100'
            "
          >
            Sim
          </span>
        </div>

        <div
          class="mx-5 cursor-pointer block p-3 rounded-lg"
          :class="
            !options.includeUppercase
              ? 'bg-gray-100'
              : 'border border-gray-200'
          "
          @click="options.includeUppercase = false"
        >
          <span
            class="text-lg font-medium mx-10"
            :class="
              !options.includeUppercase
                ? 'text-gray-900'
                : 'text-gray-100'
            "
          >
            Não
          </span>
        </div>
      </div>
      <div class="mt-10 max-w-lg mx-auto text-center">
        <button
          type="submit"
          class="w-40 px-5 py-3 text-sm font-medium text-white bg-gray-800 rounded-lg"
        >
          Gerar senha
        </button>
      </div>

      <div class="mt-10 max-w-lg mx-auto text-center">
        <p class="text-gray-100 text-2xl">Sua senha gerada</p>
      </div>
      <div class="mt-10 max-w-lg mx-auto text-center">
        <label class="sr-only" for="name">Name</label>
        <input
          class="w-full p-3 text-sm border-gray-200 rounded-lg"
          placeholder="Sua senha aparecerá aqui"
          type="text"
          id="name"
        />
      </div>
    </div>
    <div class="text-center mt-3">
      <p class="text-gray-50">barreto 2022</p>
    </div>
  </div>
</template>

<script setup lang="ts">
enum PasswordLength {
  SIXTEEN = '16',
  THIRTYTWO = '32',
  SIXTYFOUR = '64',
}

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

const changePasswordLength = (length: PasswordLength) => {
  options.passwordLength = length;
};
</script>
