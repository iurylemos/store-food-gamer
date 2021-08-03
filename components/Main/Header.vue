<template>
  <header class="text-gray-700 body-font border-b border-gray-200 bg-white">
    <div
      class="container mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center"
    >
      <div
        class="flex title-font font-medium items-center text-white mb-4 md:mb-0"
      >
        <!-- <div
          class="w-10 h-10 text-white p-2 rounded-full bg-cover bg-origin-content"
          style="background-image: url('logo_index.png')"
        ></div> -->
        <solid-badge-check-icon class="w-12 h-12 text-purple-800 p2" />
        <input
          type="text"
          placeholder="Digite aqui..."
          class="h-10 ml-4 border-purple-800 bg-white text-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-800"
        />
        <solid-book-open-icon class="w-10 h-10 text-purple-800 p2 ml-5" />
        <nuxt-link
          class="ml-1 text-gray-800 hover:text-purple-800 font-medium p-1"
          to="/cardapio"
          >Cardápio
        </nuxt-link>
      </div>
      <nav
        class="md:ml-auto flex flex-wrap items-center text-base justify-center"
      >
        <nuxt-link
          to="/"
          class="mr-5 text-gray-800 hover:text-purple-800 font-medium"
        >
          <solid-home-icon class="w-5 h-5 text-purple-800 p2 ml-2" />
          Inicio</nuxt-link
        >
        <a
          class="cursor-pointer mr-5 text-gray-800 hover:text-purple-800 font-medium"
        >
          <solid-shopping-bag-icon class="w-5 h-5 text-purple-800 p2 ml-3" />
          Pedido</a
        >
        <a
          class="mr-5 text-gray-800 cursor-pointer hover:text-purple-800 font-medium"
          >Criar conta</a
        >
      </nav>
      <nuxt-link
        class="ml-5 botao-primario font-medium hover:text-gray-800"
        to="/login"
        >Entrar</nuxt-link
      >
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
