<template>
  <header class="text-gray-700 body-font border-b border-gray-200 bg-gray-800">
    <div
      class="container mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center"
    >
      <div
        class="flex title-font font-medium items-center text-white mb-4 md:mb-0"
      >
        <div
          class="w-10 h-10 text-white p-2 rounded-full bg-cover bg-origin-content"
          style="background-image: url('logo_index.png')"
        ></div>
        <input
          type="text"
          placeholder="Digite aqui..."
          class="h-10 ml-4 border-white bg-gray-800 text-white rounded-lg"
        />
        <nuxt-link
          class="ml-5 text-white hover:text-green-400 font-medium"
          to="/cardapio"
          >Cardápio</nuxt-link
        >
      </div>
      <nav
        class="md:ml-auto flex flex-wrap items-center text-base justify-center"
      >
        <nuxt-link
          to="/login"
          class="mr-5 text-white hover:text-green-400 font-medium"
          >Inicio</nuxt-link
        >
        <a class="mr-5 text-white hover:text-green-400 font-medium">Combos</a>
        <a class="mr-5 text-white hover:text-green-400 font-medium"
          >Criar conta</a
        >
      </nav>
      <nuxt-link class="ml-5 botao-primario" to="/login">Entrar</nuxt-link>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      isLogged: false
    };
  }
};
</script>
