<template>
  <header class="text-gray-700 body-font border-b border-gray-200 bg-gray-800">
    <div
      class="container mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center"
    >
      <a
        class="flex title-font font-medium items-center text-white mb-4 md:mb-0"
        href="https://tailblocks.cc"
        target="_blank"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          stroke="currentColor"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          class="w-10 h-10 text-white p-2 bg-yellow-500 rounded-full"
          viewBox="0 0 24 24"
        >
          <path
            d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"
          ></path>
        </svg>
        <span class="ml-3 text-xl">SPRINGFOOD</span>
      </a>
      <nav
        class="md:ml-auto flex flex-wrap items-center text-base justify-center"
      >
        <a class="mr-5 text-yellow-300 hover:text-white font-normal">Inicio</a>
        <a class="mr-5 text-yellow-300 hover:text-white font-normal"
          >Cardápio</a
        >
        <a class="mr-5 text-yellow-300 hover:text-white font-normal">Combos</a>
        <a class="mr-5 text-yellow-300 hover:text-white font-normal"
          >Promoções</a
        >
      </nav>
      <button
        class="inline-flex items-center font-normal bg-gray-200 border-0 py-1 px-3 focus:outline-none hover:bg-gray-300 rounded text-base mt-4 md:mt-0"
      >
        Sair
      </button>
    </div>
  </header>
</template>
