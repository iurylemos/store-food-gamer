<template>
  <header class="text-gray-700 body-font border-b border-gray-200 bg-white">
    <div
      class="container mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center"
    >
      <div
        class="flex title-font font-medium items-center text-white mb-4 md:mb-0"
      >
        <solid-badge-check-icon class="w-12 h-12 text-purple-800 p2" />
        <input
          type="text"
          placeholder="Digite aqui..."
          class="h-10 ml-4 border-purple-800 bg-white text-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-800"
        />
        <solid-book-open-icon class="w-11 h-11 text-purple-800 p2 ml-5" />
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
          <solid-home-icon class="w-6 h-6 text-purple-800 p2 ml-2"
        /></nuxt-link>
        <a
          class="cursor-pointer mr-5 text-gray-800 hover:text-purple-800 font-medium"
        >
          <DropAccount />
        </a>
        <a
          class="mr-5 text-gray-800 cursor-pointer hover:text-purple-800 font-medium"
          @click="toogleModal"
        >
          <solid-shopping-bag-icon class="w-6 h-6 text-purple-800 p2 ml-3" />
          <ModalOrder @toogle-modal="toogleModal" :modal="modal" />
        </a>
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
import DropAccount from "./DropAccount.vue";
import ModalOrder from "./ModalOrder.vue";

export default {
  name: "Header",
  components: { DropAccount, ModalOrder },
  data() {
    return {
      modal: false,
      isLogged: false
    };
  },
  methods: {
    toogleModal() {
      this.modal = !this.modal;
    }
  }
};
</script>
