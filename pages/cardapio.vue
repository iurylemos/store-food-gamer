<template>
  <div>
    <Header />
    <div class="flex" v-cloak id="dribbleShot">
      <div class="main px-16 border-r border-gray-200">
        <div class="h-12 mt-8 flex items-center">
          <h6 class="font-bold text-lg mx-10">{{ title }}</h6>
          <div
            class="flex items-center ml-auto bg-gray-200 self-stretch custom-rounded px-4 w-2/3"
          >
            <!-- <i class="fa fa-search"></i> -->
            <solid-search-icon class="w-5 h-5 text-purple-800 p2" />
            <input
              type="text"
              class="px-4 self-stretch bg-transparent flex-grow outline-none"
              placeholder="Pesquisar"
            />
          </div>
        </div>
        <div class="grid grid-cols-3 bg-orange-100 mt-12 rounded-lg">
          <div>
            <img
              src="https://image.freepik.com/free-vector/vector-cartoon-illustration-traditional-set-fast-food-meal_1441-331.jpg"
              alt="fooood"
              class="self-end"
            />
          </div>
          <div class="row-auto flex flex-col justify-center items-center">
            <h3 class="tracking-wide text-orange-600 text-lg ml-6">
              30 dias de entrega grátis!&nbsp;&nbsp;&nbsp;🎉
            </h3>
            <h5 class="text-xs text-gray-500">
              Valido somente para pedidos acima de 10 R$
            </h5>
          </div>
          <div class="flex justify-end items-end pb-4 pr-4">
            <a class="font-hairline text-orange-500" href=""
              >Saiba como participar <i class="ml-3 fa fa-arrow-right"></i
            ></a>
          </div>
        </div>
        <div class="flex mt-12 items-end">
          <h3 class="text-xl font-bold">Restaurantes</h3>
          <img
            src="https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/thumbs/120/apple/237/hamburger_1f354.png"
            class="mx-4 h-8 w-8"
            alt=""
          />
          <button
            class="ml-auto rounded-full p-2 bg-orange-600 hover:bg-orange-500 hover:shadow-lg text-white cursor-pointer text-sm"
          >
            <i class="fa fa-clock mx-2"></i>
            <span class="font-hairline">Delivery: </span><span>Now</span>
            <i class="fa fa-chevron-down mx-2"></i>
          </button>
        </div>
        <div class="grid grid-cols-9 gap-6 mt-12">
          <div
            @click="activeCategory = cat.id"
            class=" border rounded-full p-2 flex flex-col items-center shadow-xl cursor-pointer transition-colors duration-700 ease-in-out"
            :class="{ 'bg-yellow-400': cat.id == activeCategory }"
            v-for="cat in categories"
            :key="cat.id"
          >
            <div class="border rounded-full p-2 bg-white">
              <img class="h-12 w-12" :src="cat.icon" alt="" />
            </div>
            <p class="mt-3 mb-10 font-bold  text-xs">{{ cat.text }}</p>
          </div>
          <button
            class="h-10 rounded-lg self-center hover:shadow-xl flex justify-center items-center bg-gray-100 p-3 ml-auto"
          >
            <i class="fa fa-chevron-right"></i>
          </button>
        </div>
        <div class="mt-12 grid grid-cols-3 gap-10">
          <div class="flex flex-col" v-for="food in foodItems" :key="food.id">
            <div
              class="shadow-lg relative h-40 custom-rounded"
              :style="{
                backgroundSize: 'cover',
                backgroundRepeat: 'no-repeat',
                backgroundImage: 'url(\'' + food.image + '\')'
              }"
            >
              <div
                class="absolute bottom-0 left-0 w-1/3 bg-gray-200 rounded-tr-lg p-2 text-center text-xs"
              >
                <span class="font-bold">{{ food.prepTimeValue }}</span>
                {{ food.prepTimeUnit }}
              </div>
            </div>
            <p class="mt-4 font-medium">{{ food.title }}</p>
            <div class="mt-2 flex items-center">
              <span class="text-xs"
                ><i class="fa fa-star"></i> {{ food.rating }}</span
              >
              <span class="text-gray-600 font-hairline text-xs mx-4">{{
                food.cat1
              }}</span>
              <span class="text-gray-600 font-hairline text-xs mx-4">{{
                food.cat2
              }}</span>
              <span class="text-gray-600 font-hairline text-xs mx-4">{{
                food.range
              }}</span>
            </div>
          </div>
        </div>
      </div>
      <div class="bg-gray-100 sidebar flex flex-col">
        <div class="px-6">
          <div class="h-12 mt-0 flex justify-end items-center">
            <i class="fa fa-user"></i>
            <div
              class="rounded-lg bg-yellow-400 px-3 font-bold text-xs py-1 ml-6"
            >
              3
            </div>
          </div>
          <div class="mt-8">
            <p class="font-medium text-xl">Meu Pedido 😎</p>
          </div>
          <div
            class="mt-12 p-6 bg-purple-800 custom-rounded font-hairline text-xs"
          >
            <div class="flex justify-between items-center">
              <p class="text-white">625, Rua Francisco da Silva, Maracanaú</p>
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
            v-for="(item, index) in cartItems"
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
            <div class="col-span-2 grid grid-cols-3 text-xxs font-semibold ">
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
              <i class="fa fa-car m-auto text-orange-500"></i>
            </div>
            <div class="col-span-2 grid grid-cols-3 text-xxs font-semibold ">
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
        </div>
        <div class="flex-grow flex flex-col pl-6 justify-end">
          <div class="flex justify-between items-center border-b-2 pb-2">
            <span>Total:</span>
            <span class="text-xl font-medium pr-6">$25.97</span>
          </div>
          <div class="flex justify-between pt-4 text-xs font-bold">
            <div class="flex flex-col">
              <span>Persons</span>
              <div class="flex items-center mt-3">
                <span class="border border-r-0 p-2 rounded-l-lg">-</span>
                <span class="border-b border-t p-2 ">1</span>
                <span class="border border-l-0 p-2 rounded-r-lg">+</span>
              </div>
            </div>
            <div class="ml-auto bg-yellow-400 p-6 rounded-l-lg">
              Conferir <i class="ml-3 fa fa-arrow-right"></i>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="flex h-10">
      <div class="flex-grow px-16 main border-r border-gray-200"></div>
      <div class="sidebar bg-gray-100"></div>
    </div>
  </div>
</template>

<style>
[v-cloak] {
  display: none;
}

#dribbleShot {
  margin-top: 0;
}

.main {
  flex: 3;
}

.sidebar {
  flex: 1;
}

.custom-rounded {
  border-radius: 25px;
}

.custom-tr-rounded {
  border-radius: 0 25px 0 0;
}

.timer {
  background: rgba(217, 194, 105, 0.2);
}

.text-xxs {
  font-size: 0.7rem;
}
</style>

<script>
import Header from "../components/Main/Header.vue";

export default {
  components: {
    Header
  },
  data() {
    return {
      title: "Store Food Gamer",
      activeCategory: 1,
      categories: [
        {
          id: 1,
          text: "All",
          icon: "https://image.flaticon.com/icons/svg/1046/1046874.svg",
          isActive: true
        },
        {
          id: 2,
          text: "Pizza",
          icon: "https://image.flaticon.com/icons/svg/766/766226.svg",
          isActive: false
        },
        {
          id: 3,
          text: "Asian",
          icon: "https://image.flaticon.com/icons/svg/2689/2689335.svg",
          isActive: false
        },
        {
          id: 4,
          text: "Burgers",
          icon: "https://image.flaticon.com/icons/svg/260/260077.svg",
          isActive: false
        },
        {
          id: 5,
          text: "Barbecue",
          icon: "https://image.flaticon.com/icons/svg/1161/1161684.svg",
          isActive: false
        },
        {
          id: 6,
          text: "Desserts",
          icon: "https://image.flaticon.com/icons/svg/1784/1784077.svg",
          isActive: false
        },
        {
          id: 7,
          text: "Thai",
          icon: "https://image.flaticon.com/icons/svg/2321/2321808.svg",
          isActive: false
        },
        {
          id: 8,
          text: "Sushi",
          icon: "https://image.flaticon.com/icons/svg/2558/2558357.svg",
          isActive: false
        }
      ],
      foodItems: [
        {
          title: "Bagel Story",
          image:
            "https://hips.hearstapps.com/hmg-prod.s3.amazonaws.com/images/25008305-442083466194421-4458779521922891776-n-1517333246.jpg?crop=1xw:1xh;center,top&resize=480:*",
          prepTimeValue: "25 - 30",
          prepTimeUnit: "min",
          rating: 4.7,
          cat1: "Deli",
          cat2: "Bagels",
          range: "$$"
        },
        {
          title: "Dessert Rose",
          image:
            "https://images.mygoodtimes.in/wp-content/uploads/2018/12/08210525/Bakers-Copy.jpg",
          prepTimeValue: "30 - 35",
          prepTimeUnit: "min",
          rating: 4.5,
          cat1: "Cafes",
          cat2: "Desserts",
          range: "$"
        },
        {
          title: "Barbecue Nation",
          image:
            "https://chowhound1.cbsistatic.com/thumbnail/370/0/chowhound1.cbsistatic.com/assets/2012/08/30453_RecipeImage_620x413_grilled_chicken_nectarine.jpg",
          prepTimeValue: "40 - 60",
          prepTimeUnit: "min",
          rating: 4.6,
          cat1: "Barbecue",
          cat2: "Chicken",
          range: "$$$"
        }
      ],
      cartItems: [
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
  }
};
</script>
