<template>
  <div class="bg-gray-900 py-6 sm:py-8 lg:py-12">
    <div class="mx-auto max-w-screen-2xl px-4 md:px-8">
      <div
        class="flex flex-col overflow-hidden rounded-lg sm:flex-row md:h-[35rem]"
      >
        <div
          class="flex w-full flex-col p-4 sm:w-1/2 sm:p-8 md:p-16 lg:p-10 lg:w-[46%] round-corners"
        >
          <h2
            class="mb-4 lg:mt-16 lg:mb-8 text-xl font-bold text-white md:text-2xl md:font-medium lg:text-5xl lg:font-medium lg:leading-[56px]"
          >
            We do campaigns that works well for your idea
          </h2>

          <p class="mb-8 max-w-lg text-gray-400 text-xl">
            Our documentary campaigns feature leading figures, organisations and
            leaders, in open and candid discussions about transformative
            strategies and mindsets. Addressing complex trends.
          </p>

          <div class="mb-auto mt-6 ml-2">
            <a
              href="#"
              class="inline-block text-center text-lg font-bold bg-gradient-to-r from-indigo-600 to-purple-500 bg-clip-text text-transparent outline-none ring-indigo-300 transition duration-100 hover:bg-gray-100 focus-visible:ring active:bg-gray-200 md:text-base"
              >All compaigns
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="2.5"
                stroke="currentColor"
                class="w-4 h-4 text-purple-500 inline ml-3"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M13.5 4.5 21 12m0 0-7.5 7.5M21 12H3"
                />
              </svg>
            </a>
          </div>
        </div>

        <div
          class="order-first h-48 w-full bg-gray-900 sm:order-none sm:h-auto sm:w-1/2 lg:w-[54%]"
        >
          <img
            src="@/assets/img/movie/city.png"
            loading="lazy"
            alt="Photo by Dom Hill"
            class="h-full w-full rounded-3xl object-cover object-center"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
@media (min-width: 1400px) {
  .round-corners {
    position: relative;
  }

  .round-corners:before,
  .round-corners:after {
    content: "";
    position: absolute;
    border: solid rgb(86, 86, 86);
    border-top-left-radius: 16px;
    border-bottom-right-radius: 16px;
    width: 48px;
    height: 48px;
    pointer-events: none;
  }

  .round-corners:before {
    top: 72px;
    left: 0px;
    border-width: 1px 0 0 1px;
  }

  .round-corners:after {
    bottom: 80px;
    right: 64px;
    border-width: 0 1px 1px 0;
  }
}
</style>
