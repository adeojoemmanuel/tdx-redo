<template>
  <div class="py-24">
    <div class="mx-auto text-center w-10/12">
      <h2 class="text-gray-800 font-semibold text-3xl tracking-wide">
        Pricing plans
      </h2>
      <div class="w-11/12 sm:w-10/12 md:w-6/12 mx-auto">
        <p class="pt-2 text-gray-400 tracking-tight">
          Place your ads above others with our paid plans, with just little
          money you can place your ads to more customers on our platform
        </p>
      </div>
    </div>
    <!-- pricing cards -->
    <div class="mt-8">
      <div class="flex items-center space-x-6 justify-center py-3">
        <span class="text-sm text-gray-700 font-medium">Bill Monthly</span>
        <label
          for="unchecked"
          class="mt-1 inline-flex items-center cursor-pointer"
        >
          <span class="relative">
            <span
              class="block w-12 h-6 rounded-full shadow-inner"
              :class="planType ? 'bg-explorerGreen-300' : 'bg-gray-200'"
            ></span>
            <span
              class="absolute block w-4 bg-white h-4 mt-1 ml-3 rounded-full shadow inset-y-0 left-0 focus-within:shadow-outline transition-transform duration-300 ease-in-out"
              :class="planType ? 'transform translate-x-full' : 'ml-0.5'"
            >
              <input
                id="unchecked"
                type="checkbox"
                v-model="planType"
                class="absolute opacity-0 w-0 h-0"
              />
            </span>
          </span>
        </label>
        <span class="text-sm text-gray-700 font-medium">Bill Yearly</span>
      </div>
    </div>
    <!-- pricing cards -->
    <div
      class="flex items-center justify-center w-11/12 lg:10/12 overflow-x-scroll mx-auto space-x-12 mt-12 py-12 px-8"
    >
      <div
        class="rounded-md bg-white px-8 py-6 max-w-xs flex-shrink-0 lg:w-1/3 h-auto shadow-md transition duration-500 transform hover:bg-gray-50 hover:scale-110"
        v-for="plan in plans"
        :key="plan.id"
      >
        <div class="text-left">
          <p class="text-3xl flex items-center text-gray-800 font-medium">
            ${{ plan.price
            }}<span
              class="text-xs ml-0.5 tracking-tight font-medium text-gray-500 mt-1.5"
              >/{{ plan.type }}</span
            >
          </p>
        </div>
        <p class="text-gray-800 text-2xl font-medium pt-4">{{ plan.name }}</p>
        <p class="text-gray-400 pt-3 text-xs w-11/12 break-words">
          {{ plan.desc }}
        </p>
        <hr class="border-gray-100 py-0.5 my-10" />
        <div class="mt-6 mx-auto">
          <ul class="space-y-5">
            <li
              class="flex items-center space-x-2"
              v-for="feature in plan.features"
              :key="feature.id"
            >
              <div class="rounded-full bg-green-200 p-0.5">
                <svg
                  class="text-green-400 stroke-current opacity-80 h-4 w-4 mx-auto text-center"
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="3"
                    d="M5 13l4 4L19 7"
                  />
                </svg>
              </div>
              <span class="text-sm text-gray-600 font-medium">
                {{ feature.name }}</span
              >
            </li>
          </ul>
        </div>
        <div class="w-10/12 pt-10">
          <button
            class="bg-transparent text-gray-800 border border-explorerGreen-200 hover:border-transparent hover:bg-explorerGreen-300 hover:text-white tracking-wide text-center w-full py-3 rounded-full transition duration-300"
          >
            Get Started
          </button>
        </div>
      </div>
    </div>
    <!-- pricing cards -->
    <!-- pricing area -->
  </div>
</template>

<script>
export default {
  name: "Property",
  data: () => {
    return {
      showYearly: true,
      showMonthly: true,
      planType: false,
      plans: [
        {
          id: 1,
          name: "Basic Plan",
          desc:
            "Our basic plan gives you tools to enable new and low income businesses grow on our platform and increase customer base",
          type: "Monthly",
          price: 20,
          yrPrice: 200,
          features: [
            { id: 1, name: "2 top ads monthly" },
            { id: 2, name: "3 premium ads monthly" },
          ],
        },
        {
          id: 2,
          name: "Business Plan",
          type: "Monthly",
          desc:
            "Our business is the most popular plan, it gives you features to grow your business rapidly and grow your customer base",
          price: 30,
          yrPrice: 300,
          features: [
            { id: 1, name: "5 top ads monthly" },
            { id: 2, name: "10 premium ads monthly" },
          ],
        },
        {
          id: 3,
          name: "Premium Plan",
          type: "Monthly",
          desc:
            "Our premium plan gives you all features to grow your business as fast as possible within a short time and its also useful for large businesses",
          price: 60,
          yrPrice: 600,
          features: [
            { id: 1, name: "20 top ads monthly" },
            { id: 2, name: "Unlimited premium ads monthly" },
          ],
        },
      ],
    };
  },
  methods: {
    changeType(currentType) {
      this.plans.forEach((plan) => {
        if (currentType == 1) {
          (plan.type = "Yearly"), (plan.price = plan.yrPrice);
        } else if (currentType === 2) {
          plan.type = "Monthly";
          plan.price = plan.yrPrice / 10;
        }
      });
    },
  },
  watch: {
    planType: {
      immediate: true,
      handler: function(plan) {
        plan ? this.changeType(1) : this.changeType(2)
      }
    }
  }
};
</script>

<style lang="css" scoped>
</style>
