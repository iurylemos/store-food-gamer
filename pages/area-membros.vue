<template>
  <div>
    <div class="flex">
      <h1>Area Membros</h1>
      <button class="botao-secundario" @click="sair()">Sair</button>
    </div>
    <hr />
    <p>Produtos Disponíveis &#8628;</p>
    <ul class="text-lg text-gray-700 font-semibold space-y-4">
      <li v-for="product in products" :key="product._id">
        {{ product.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  middleware: "auth",
  data() {
    return {
      products: []
    };
  },
  created() {
    this.loadProducts();
  },
  methods: {
    async loadProducts() {
      try {
        const res = await this.$axios.$get("http://localhost:8080/products");
        this.products = res;
      } catch (error) {
        console.error(err);
      }
    },
    async sair() {
      await this.$auth.logout();
    }
  }
};
</script>
