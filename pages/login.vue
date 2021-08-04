<template>
  <div class="flex h-screen items-center ">
    <div
      class="tela flex w-full max-w-3xl mx-auto rounded-lg shadow-xl content-center"
    >
      <div
        class="esquerda xl:block rounded-l-lg bg-cover bg-center w-1/2"
        style="background-image: url('logo.png')"
      ></div>
      <div class="direita h-full w-1/2  py-4 text-center">
        <form class="bg-white">
          <div class="p-3 pb-8 text-gray-700 text-center">
            <h1 class="text-gray-900 text-xl mb-2 font-bold">
              STORE FOOD GAMER
            </h1>
            <p class="text-xl">Entre com sua conta</p>
          </div>

          <div class="inline-block w-4/5 text-left mb-4">
            <label
              class="text-left text-gray-700 font-bold mb-5"
              for="e-mail"
              >E-mail</label
            >
            <div class="flex">
            <solid-user-icon class="h-11 w-11 rounded-l-md inline-flex items-center px-3 border-t bg-white border-l border-b border-gray-300 text-gray-500 shadow-sm text-sm" />
            <input
              class="w-full shadow-inner appearance-none border rounded-r-lg py-2 px-3 bg-gray-200 text-gray-700 leading-normal border-t bg-white border-l border-b border-gray-300 text-gray-500 shadow-sm text-sm focus:outline-none focus:shadow-outline focus:border-yellow-500"
              id="e-mail"
              type="email"
              required
              placeholder="Digite seu e-mail..."
            />
            </div>
          </div>
          <div class="inline-block w-4/5 text-left mb-4">
            <label
              class="text-left text-gray-700 font-bold mb-5"
              for="senha"
              >Senha</label
            >
            <div class="flex">
            <solid-LockClosed-icon class="h-11 w-11 rounded-l-md inline-flex items-center px-3 border-t bg-white border-l border-b border-gray-300 text-gray-500 shadow-sm text-sm" />
            <input
              class="w-full shadow-inner appearance-none border rounded-r-lg py-2 px-3 bg-gray-200 text-gray-700 leading-normal border-t bg-white border-l border-b border-gray-300 text-gray-500 shadow-sm text-sm focus:outline-none focus:shadow-outline focus:border-yellow-500"
              id="senha"
              type="password"
              required
              placeholder="Digite sua senha..."
            />
            </div>
            <div class="links flex items-center justify-center m-4">
              <a
                class="align-baseline font-bold text-xs text-blue-500 hover:text-blue-800"
                href="#"
                >Esqueci minha senha</a
              >
              <span class="mx-2">|</span>
              <nuxt-link
                class="align-baseline font-bold text-xs text-blue-500 hover:text-blue-800"
                to="/cadastro"
                >Registre-se</nuxt-link
              >
            </div>
          </div>
          

          <div class="flex w-full items-center justify-center sm:mb-2">
            <button
              class="flex items-center justify-center w-64 bg-purple-500  text-gray-50 font-bold rounded hover:bg-purple-600  shadow-md py-2"
            >
              <span class="mr-2 text-sm  lading-normal">ENTRAR</span>

            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      login: {
        email: "",
        password: ""
      }
    };
  },
  methods: {
    loginUser() {
      this.$auth
        .loginWith("local", {
          data: this.login
        })
        .then(auth => {
          console.log("sucesso auth", auth);
        })
        .catch(err => {
          console.log("error", err);
        });
    }
  }
};
</script>
<style scoped>
@media (max-width: 888px) {
  
  .tela {

    display: inherit;
    flex-direction: column;
    align-items: center;
    height: 100%;
  }
  .esquerda {
    width: 100%;
    height: 100%;
    border-radius: 0;
  }
  .direita {
    width: 100%;
    height: 100%;
  }
}

</style>
