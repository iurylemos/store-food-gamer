<template>
  <div id="dropdown" class="relative inline-block pt-1">
    <button @click="isOpen = true">
      <solid-user-circle-icon
        class="w-6 h-6 text-purple-800 ml-2"
      ></solid-user-circle-icon>
    </button>

    <div
      v-if="isOpen"
      @click="isOpen = false"
      class="fixed inset-0"
      tabindex="-1"
    ></div>

    <transition
      enter-class="opacity-0 transform scale-90 transition-all"
      enter-active-class="transition ease-out duration-75"
      enter-to-class="opacity-100 transform scale-100"
      leave-class="opacity-100 transform scale-100"
      leave-active-class="transition ease-in duration-75"
      leave-to-class="opacity-0 transform scale-90"
    >
      <div
        v-if="isOpen"
        class="absolute right-0 mt-3 text-left z-75 transform origin-top-right"
      >
        <div class="w-64 bg-gray-200 rounded-lg shadow-lg">
          <div class="flex items-center px-6 py-4">
            <img
              class="h-10 w-10 rounded-full flex-no-shrink"
              src="https://media-exp1.licdn.com/dms/image/C4D03AQFoipOrqCIzFA/profile-displayphoto-shrink_800_800/0/1600990922125?e=1633564800&v=beta&t=ByNXB2A_tCcS-VCkptASGewYEN79ZxGS1ndXQ2WjesQ"
              alt=""
            />
            <div class="ml-4">
              <p class="font-semibold text-gray-900 leading-none">
                Ian Oliveira
              </p>
              <p>
                <a
                  href="#"
                  class="text-sm text-gray-600 leading-none hover:underline"
                  >View Profile</a
                >
              </p>
            </div>
          </div>
          <div class="border-t-2 border-gray-200 py-1">
            <a href="#" class="block px-6 py-3 leading-tight hover:bg-gray-200"
              >Configurações e privacidade</a
            >
            <a href="#" class="block px-6 py-3 leading-tight hover:bg-gray-200"
              >Pagamento</a
            >
          </div>
          <div class="border-t-2 border-gray-200 py-1">
            <a href="#" class="block px-6 py-3 leading-tight hover:bg-gray-200"
              >Ajuda</a
            >
            <a href="#" class="block px-6 py-3 leading-tight hover:bg-gray-200"
              >Meu histórico</a
            >
          </div>
          <form
            class="border-t-2 border-gray-200 py-1"
            action="#"
            method="POST"
          >
            <button
              class="block w-full px-6 py-3 text-left leading-tight hover:bg-gray-200"
            >
              Sair
            </button>
          </form>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: "DropAccount",
  data() {
    return {
      isOpen: false
    };
  }
};
</script>
