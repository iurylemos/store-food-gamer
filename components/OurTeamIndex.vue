<template>
  <section class="text-gray-700 body-font border-t border-gray-200">
    <div class="container px-5 py-24 mx-auto">
      <div class="flex flex-col text-center w-full mb-20">
        <h1
          class="sm:text-3xl text-2xl font-medium title-font mb-4 text-gray-900"
        >
          Nosso time
        </h1>
        <p class="lg:w-2/3 mx-auto leading-relaxed text-base">
          Whatever cardigan tote bag tumblr hexagon brooklyn asymmetrical
          gentrify, subway tile poke farm-to-table. Franzen you probably haven't
          heard of them.
        </p>
      </div>
      <div class="flex flex-wrap -m-2">
        <div
          class="p-2 lg:w-1/3 md:w-1/2 w-full"
          v-for="dev in developers"
          :key="dev.name"
        >
          <div
            class="h-full flex items-center border-gray-200 border p-4 rounded-lg"
          >
            <img
              alt="team"
              class="w-16 h-16 bg-gray-100 object-cover object-center flex-shrink-0 rounded-full mr-4"
              src="https://dummyimage.com/108x98/edf2f7/a5afbd"
            />
            <div class="flex-grow">
              <h2 class="text-gray-900 title-font font-medium">
                {{ dev.name }}
              </h2>
              <p class="text-gray-500">{{ dev.office }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      developers: [
        {
          name: "Iury Lemos",
          office: "Software Developer"
        },
        {
          name: "Venicius",
          office: "Software Developer"
        }
      ]
    };
  }
};
</script>
