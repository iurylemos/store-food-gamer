<template>
  <div
    v-if="modal"
    @click="toggleModal"
    class="fixed z-10 inset-0 overflow-y-auto"
  >
    <div
      class="flex items-end justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0"
    >
      <div class="fixed inset-0 transition-opacity" aria-hidden="true">
        <div class="absolute inset-0 bg-gray-500 opacity-75"></div>
      </div>
      <span
        class="hidden sm:inline-block sm:align-middle sm:h-screen"
        aria-hidden="true"
        >&#8203;</span
      >
      <div
        class="inline-block align-bottom bg-white rounded-xl text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg sm:w-full"
        role="dialog"
        aria-modal="true"
        aria-labelledby="modal-headline"
      >
        <div
          class="header-modal py-3 px-4 bg-purple-800 text-white font-semibold shadow-lg text-lg"
        >
          Meu Pedido 😎
        </div>
        <div v-if="!orders.length" class="body-modal p-4">
          <div class="content">
            <blockquote>
              <p class="text-lg font-semibold">
                “Não há pedidos em sua sacola. Verifique se tem algo que deseja,
                e faça já o seu pedido.”
              </p>
            </blockquote>
          </div>
        </div>
        <div v-else class="body-modal p-4">
          <div class="content">
            <div class="px-6">
              <div
                class="p-6 bg-purple-800 custom-rounded font-hairline text-xs"
              >
                <div class="flex justify-between items-center">
                  <p class="text-white">
                    625, Rua Francisco da Silva, Maracanaú
                  </p>
                  <p class="text-yellow-400 cursor-pointer">Editar</p>
                </div>
                <div class="flex items-center mt-4">
                  <div class="rounded-lg px-2 py-1 timer">
                    <i class="fa fa-clock text-yellow-400"></i>
                  </div>
                  <p class="text-white mx-3">35 min</p>
                  <p class="text-yellow-400 cursor-pointer ml-auto">
                    Tempo estimado
                  </p>
                </div>
              </div>
              <div
                v-for="(item, index) in orders"
                class="grid grid-cols-4 gap-1 mb-5"
                :class="{ 'mt-12': index == 0 }"
                :key="item.id"
              >
                <div
                  class="h-10 rounded-lg"
                  :style="{
                    backgroundSize: 'cover',
                    backgroundRepeat: 'no-repeat',
                    backgroundImage: 'url(\'' + item.image + '\')'
                  }"
                ></div>
                <div
                  class="col-span-2 grid grid-cols-3 text-xxs font-semibold "
                >
                  <p class="flex justify-center items-center">
                    {{ item.quantity }} <span class="ml-1">x</span>
                  </p>
                  <p class="col-span-2 flex items-center">{{ item.title }}</p>
                </div>
                <div
                  class="flex justify-end items-center text-gray-600 font-hairline text-xs"
                >
                  ${{ item.price }}
                </div>
              </div>
              <div class="grid grid-cols-4 gap-1 mb-5">
                <div class="h-10 rounded-lg bg-orange-200 flex">
                  <solid-truck-icon />
                </div>
                <div
                  class="col-span-2 grid grid-cols-3 text-xxs font-semibold "
                >
                  <p class="col-span-2 flex justify-center items-center">
                    Delivery
                  </p>
                  <p class="flex items-center"></p>
                </div>
                <div
                  class="flex justify-end items-center text-gray-600 font-hairline text-xs"
                >
                  $0.00
                </div>
              </div>
              <div class="grid grid-cols-4 gap-1 mb-2">
                <div class="h-10 rounded-lg bg-orange-200 flex">
                  <solid-currency-dollar-icon />
                </div>
                <div
                  class="col-span-2 grid grid-cols-3 text-xxs font-semibold "
                >
                  <p class="col-span-2 flex justify-center items-center">
                    Valor total
                  </p>
                  <p class="flex items-center"></p>
                </div>
                <div
                  class="flex justify-end items-center text-gray-600 font-hairline text-xs"
                >
                  $0.00
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="footer-modal px-4 pb-4">
          <div class="flex flex-row-reverse">
            <button
              class="ml-2 bg-purple-800 text-white px-8 rounded-lg py-2 hover:bg-purple-900 t"
              @click="confirmOrder"
            >
              OK
            </button>
            <button
              class="hover:bg-gray-200 hover:text-gray-900 text-gray-600 px-8 rounded-lg py-2"
              @click="toggleModal"
            >
              Cancelar
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalOrder",
  data() {
    return {
      orders: [
        {
          title: "BBQ Burger",
          image:
            "https://hips.hearstapps.com/pop.h-cdn.co/assets/cm/15/05/54ca71fb94ad3_-_5summer_skills_burger_470_0808-de.jpg?crop=1xw:1.0xh;center,top&resize=480:*",
          quantity: 1,
          price: 14.99
        },
        {
          title: "French Fries",
          image:
            "https://recipes.timesofindia.com/thumb/54659021.cms?width=1200&height=1200",
          quantity: 1,
          price: 9.99
        },
        {
          title: "Cheese Sauce",
          image:
            "https://www.pepperscale.com/wp-content/uploads/2017/10/spicy-nacho-cheese.jpeg",
          quantity: 1,
          price: 0.99
        }
      ]
    };
  },
  props: {
    modal: {
      type: Boolean,
      default: false,
      required: true
    }
  },
  methods: {
    toggleModal() {
      //   this.modal = !this.modal;
      this.$emit("toogle-modal");
    },
    confirmOrder() {
      this.$emit("toogle-modal");
    }
  }
};
</script>
