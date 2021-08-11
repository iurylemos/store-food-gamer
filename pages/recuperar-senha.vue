<template>
  <div class="min-h-screen bg-gray-100 flex items-center">
    <div
      class="container mx-auto max-w-md shadow-md hover:shadow-lg transition duration-300"
    >
      <div class="py-12 p-10 bg-white rounded-xl">
        <div class="mb-4 text-center pb-4">
          <h1 class="text-2xl font-bold text-green-900">
            Recuperar senha de acesso
          </h1>
        </div>
        <div class="">
          <label
            class="mr-4 text-gray-700 font-bold inline-block mb-2"
            for="name"
          >
            Email
          </label>
          <input
            type="text"
            class="border bg-gray-100 py-2 px-4 w-94 outline-none focus:ring-2 focus:ring-green-700 rounded"
            placeholder="@email"
          />
        </div>
        <button
          class="
            w-full
            mt-6
            text-indigo-50
            font-bold
            bg-green-900
            py-3
            rounded-md
            hover:bg-green-700
            transition
            duration-300
          "
        >
          ENVIAR
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped></style>
