<template>
  <div>
    <div
      class="h-auto mx-auto  bg-gradient-to-b from-explorerGreen-300 to-explorerGreen-500 py-28 lg:py-24"
    >
      <div class="flex justify-center w-full mx-auto text-center">
        <div
          class="flex items-center justify-start mx-auto space-x-2 text-center"
        >
          <p class="font-light text-gray-100 tracking-white">
            Find anything in
          </p>
          <span
            class="flex items-center px-2 py-1 text-xs font-semibold tracking-tight text-white bg-gray-800 rounded-md  opacity-60"
          >
            <svg
              class="w-4 h-4 text-white stroke-current"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"
              />
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"
              />
            </svg>
            All Nigeria</span
          >
        </div>
      </div>
      <div class="flex justify-center w-11/12 mx-auto mt-8 text-center">
        <div class="relative flex items-center w-11/12 text-gray-600 md:w-6/12">
          <input
            type="search"
            name="serch"
            placeholder="Type your search here"
            class="w-full px-5 py-3 pr-10 text-sm placeholder-gray-400 bg-white border-0 border-transparent rounded  h-14 focus:outline-none ring-transparent focus:ring-transparent"
          />
          <button
            type="submit"
            @click.prevent="goSearch"
            class="absolute top-0 right-0 w-16 text-center bg-yellow-500 border-transparent rounded-r  h-14 focus:ring-0 focus:outline-none"
          >
            <svg
              class="w-4 h-4 mx-auto text-white fill-current"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
              version="1.1"
              id="Capa_1"
              x="0px"
              y="0px"
              viewBox="0 0 56.966 56.966"
              style="enable-background: new 0 0 56.966 56.966"
              xml:space="preserve"
              width="512px"
              height="512px"
            >
              <path
                d="M55.146,51.887L41.588,37.786c3.486-4.144,5.396-9.358,5.396-14.786c0-12.682-10.318-23-23-23s-23,10.318-23,23  s10.318,23,23,23c4.761,0,9.298-1.436,13.177-4.162l13.661,14.208c0.571,0.593,1.339,0.92,2.162,0.92  c0.779,0,1.518-0.297,2.079-0.837C56.255,54.982,56.293,53.08,55.146,51.887z M23.984,6c9.374,0,17,7.626,17,17s-7.626,17-17,17  s-17-7.626-17-17S14.61,6,23.984,6z"
              />
            </svg>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    goSearch() {
      this.$router.push("/search");
    },
  },
};
</script>

<style scoped>
.header {
  margin: 80px auto;
}

.justify-content-md-center {
  justify-content: center !important;
}

.bg-custom {
  background: #35a84f;
}

.search-form {
  width: 100%;
  min-height: 55px;
}

.border-none {
  border: 0;
  border-radius: 0;
}

.border-none:focus {
  outline: none !important;
  box-shadow: none !important;
}
</style>