<template>
  <div class="flex h-screen items-center ">
    <div
      class="tela flex w-full max-w-3xl mx-auto rounded-xl shadow-xl content-center"
    >
      <div class="esquerda h-full w-1/2  px-4 py-4 text-center">
        <form class="bg-white">
          <div class="p-3 pb-8 text-gray-700 text-center">
            <h1 class="text-gray-900 text-xl mb-2 font-bold">
              STORE FOOD GAMER
            </h1>
            <p class="text-xl">Crie sua conta</p>
          </div>
          <div class="mb-4">
            <label
              class="block text-left ml-8 text-gray-700 font-bold mb-2"
              for="nome"
              >Nome</label
            >
            <input
              class="w-4/5 shadow-inner appearance-none border rounded py-2 px-3 bg-gray-200 text-gray-700 leading-normal focus:outline-none focus:shadow-outline focus:border-yellow-500"
              id="nome"
              type="text"
              required
              placeholder="Digite seu nome..."
            />
          </div>
          <div class="mb-4">
            <label
              class="block text-left ml-8 text-gray-700 font-bold mb-2"
              for="e-mail"
              >E-mail</label
            >
            <input
              class="w-4/5 shadow-inner appearance-none border rounded py-2 px-3 bg-gray-200 text-gray-700 leading-normal focus:outline-none focus:shadow-outline focus:border-yellow-500"
              id="nome"
              type="email"
              required
              placeholder="Digite seu e-mail..."
            />
          </div>
          <div class="mb-6">
            <label
              class="block text-left ml-8 text-gray-700 font-bold mb-2"
              for="senha"
              >Senha</label
            >
            <input
              class="w-4/5 shadow-inner appearance-none border rounded py-2 px-3 bg-gray-200 text-gray-700 mb-3 leading-normal focus:outline-none focus:shadow-outline focus:border-yellow-500"
              id="senha"
              type="password"
              required
              placeholder="Digite sua senha..."
            />
            <div class="links justify-between">
              <nuxt-link
                class="align-baseline font-bold text-xs text-blue-500 hover:text-blue-800"
                to="/login"
                >Já tem uma conta? Faça login</nuxt-link
              >
            </div>
          </div>

          <div class="flex w-full items-center justify-center sm:mb-2">
            <button
              class="w-64 bg-white  text-gray-800 font-bold rounded border-b-2 border-green-500 hover:border-green-600 hover:bg-green-500 hover:text-white shadow-md py-2"
            >
              <span class="mr-2 text-sm  lading-normal">ENTRAR</span>
            </button>
          </div>
        </form>
      </div>

      <div
        class="direita xl:block rounded-r-lg bg-cover bg-center w-1/2"
        style="background-image: url('logo2.png')"
      ></div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
@media (max-width: 888px) {
  .tela {
    flex-direction: column;
    align-items: center;
    height: 100rem;
  }
  .esquerda {
    width: 100%;
    height: 100%;
  }
  .direita {
    width: 100%;
    height: 100%;
  }
}
@media (max-width: 1278px) {
  label {
    margin-left: 42px;
  }
}

@media (max-width: 888px) {
  .tela {
    height: 100%;
    display: inherit;
  }
}
</style>
