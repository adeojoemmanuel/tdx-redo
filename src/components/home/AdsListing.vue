<template>
  <div class="w-full">
    <p class="mt-8 ml-4 text-lg tracking-wide text-gray-700 lg:ml-0 lg:mt-2">
      Trending Ads.
    </p>
    <div class="grid w-11/12 grid-cols-2 mt-6 lg:grid-cols-4 ">
      <div
        class="relative w-auto mx-2 my-6 bg-white rounded-md shadow-md"
        v-for="(ad, index) in ads"
        :key="index"
      >
        <div class="relative w-full">
          <img
            :src="`/images/${ad.previewImage}`"
            alt=""
            class="w-inherit h-inherit"
          />
          <span
            class="absolute bottom-0 left-0 px-3 py-1 text-white bg-black rounded-full opacity-60"
            >8</span
          >
        </div>
        <div
          class="absolute inset-y-0 right-0 w-8 h-8 px-1 py-1 bg-white rounded-full shadow-md cursor-pointer hover:shadow-lg"
        >
          <svg
            class="w-6 h-6 mx-auto stroke-current text-explorerGreen-200"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M11.049 2.927c.3-.921 1.603-.921 1.902 0l1.519 4.674a1 1 0 00.95.69h4.915c.969 0 1.371 1.24.588 1.81l-3.976 2.888a1 1 0 00-.363 1.118l1.518 4.674c.3.922-.755 1.688-1.538 1.118l-3.976-2.888a1 1 0 00-1.176 0l-3.976 2.888c-.783.57-1.838-.197-1.538-1.118l1.518-4.674a1 1 0 00-.363-1.118l-3.976-2.888c-.784-.57-.38-1.81.588-1.81h4.914a1 1 0 00.951-.69l1.519-4.674z"
            />
          </svg>
        </div>
        <div class="px-4 py-3">
          <router-link  to="/product" class="text-lg tracking-wide text-gray-700">{{ ad.name }}</router-link>
          <p class="text-lg text-explorerGreen-200">&#8358; {{ ad.price }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: { ads: Array },
};
</script>

<style lang="scss" scoped>
</style>