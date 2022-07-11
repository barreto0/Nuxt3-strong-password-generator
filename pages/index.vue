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
        <div class="mx-5">
          <input
            class="sr-only"
            id="option1"
            type="radio"
            tabindex="-1"
          />
          <label
            for="option1"
            class="block w-full p-3 border border-gray-200 rounded-lg"
            tabindex="0"
          >
            <span class="text-lg text-gray-100 font-medium mx-10">
              16
            </span>
          </label>
        </div>

        <div class="mx-5">
          <input
            class="sr-only"
            id="option2"
            type="radio"
            tabindex="-1"
          />
          <label
            for="option2"
            class="block w-full p-3 border border-gray-200 rounded-lg"
            tabindex="0"
          >
            <span class="text-lg text-gray-100 font-medium mx-10">
              32
            </span>
          </label>
        </div>

        <div class="mx-5">
          <input
            class="sr-only"
            id="option3"
            type="radio"
            tabindex="-1"
          />
          <label
            for="option3"
            class="block w-full p-3 border border-gray-200 rounded-lg"
            tabindex="0"
          >
            <span class="text-lg text-gray-100 font-medium mx-10">
              64
            </span>
          </label>
        </div>
      </div>

      <div class="mt-10 max-w-lg mx-auto text-center">
        <p class="text-gray-100 text-2xl">
          Incluir símbolos (!@#$%^&*)
        </p>
      </div>
      <div class="mt-5 flex justify-center">
        <div class="mx-5">
          <input
            class="sr-only"
            id="option1"
            type="radio"
            tabindex="-1"
          />
          <label
            for="option1"
            class="block w-full p-3 border border-gray-200 rounded-lg"
            tabindex="0"
          >
            <span class="text-lg text-gray-100 font-medium mx-10">
              Sim
            </span>
          </label>
        </div>

        <div class="mx-5">
          <input
            class="sr-only"
            id="option2"
            type="radio"
            tabindex="-1"
          />
          <label
            for="option2"
            class="block w-full p-3 border border-gray-200 rounded-lg"
            tabindex="0"
          >
            <span class="text-lg text-gray-100 font-medium mx-10">
              Não
            </span>
          </label>
        </div>
      </div>

      <div class="mt-10 max-w-lg mx-auto text-center">
        <p class="text-gray-100 text-2xl">Incluir Números (0-9)</p>
      </div>
      <div class="mt-5 flex justify-center">
        <div class="mx-5">
          <input
            class="sr-only"
            id="option1"
            type="radio"
            tabindex="-1"
          />
          <label
            for="option1"
            class="block w-full p-3 border border-gray-200 rounded-lg"
            tabindex="0"
          >
            <span class="text-lg text-gray-100 font-medium mx-10">
              Sim
            </span>
          </label>
        </div>

        <div class="mx-5">
          <input
            class="sr-only"
            id="option2"
            type="radio"
            tabindex="-1"
          />
          <label
            for="option2"
            class="block w-full p-3 border border-gray-200 rounded-lg"
            tabindex="0"
          >
            <span class="text-lg text-gray-100 font-medium mx-10">
              Não
            </span>
          </label>
        </div>
      </div>

      <div class="mt-10 max-w-lg mx-auto text-center">
        <p class="text-gray-100 text-2xl">
          Incluir letras caixa alta (A-Z)
        </p>
      </div>
      <div class="mt-5 flex justify-center">
        <div class="mx-5">
          <input
            class="sr-only"
            id="option1"
            type="radio"
            tabindex="-1"
          />
          <label
            for="option1"
            class="block w-full p-3 border border-gray-200 rounded-lg"
            tabindex="0"
          >
            <span class="text-lg text-gray-100 font-medium mx-10">
              Sim
            </span>
          </label>
        </div>

        <div class="mx-5">
          <input
            class="sr-only"
            id="option2"
            type="radio"
            tabindex="-1"
          />
          <label
            for="option2"
            class="block w-full p-3 border border-gray-200 rounded-lg"
            tabindex="0"
          >
            <span class="text-lg text-gray-100 font-medium mx-10">
              Não
            </span>
          </label>
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
