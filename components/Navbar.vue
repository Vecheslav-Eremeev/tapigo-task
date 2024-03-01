<template>
  <header class="bg-indigo-100 text-indigo-700">
    <nav
      class="mx-auto flex max-w-7xl items-center justify-between lg:px-8"
      aria-label="Global"
    >
      <div class="flex-1">
        <a href="#" class="-m-1.5 p-1.5">
          <img
            class="h-8 w-auto"
            src="@/assets/logo/tapigo_logo.svg"
            alt="logo"
          />
        </a>
      </div>
      <div class="flex gap-x-12">
        <nuxt-link
          to="/movie"
          class="text-sm font-semibold leading-6"
          >Movie</nuxt-link
        >
        <nuxt-link
          to="/benua"
          class="text-sm font-semibold leading-6"
          >Benua</nuxt-link
        >
      </div>
      <div class="flex flex-1 justify-end">
        <nuxt-link to="/" class="text-sm font-semibold leading-6 text-gray-900"
          >Logout<span aria-hidden="true">&rarr;</span></nuxt-link
        >
      </div>
    </nav>
  </header>
</template>
