<template>
  <div>
    <nav
      id="nav-header"
      class="z-1 px-8 sm:px-16 py-4 sm:py-1 w-screen h-auto shadow-sm sm:flex sm:justify-between sm:items-center"
    >
      <div class="flex justify-between h-auto items-center">
        <div class="w-16 h-16 sm:w-20 sm:h-20">
          <router-link to="/">
            <img src="/img/logo.png" alt="logo" />
          </router-link>
        </div>
        <div class="sm:hidden">
          <button
            v-on:click="isOpen = !isOpen"
            class="text-orange-600 focus:outline-none"
            type="button"
          >
            <svg
              class="fill-current h-8 w-8"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                v-if="!isOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h8m-8 6h16"
              />
              <path
                v-if="isOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
      </div>
      <ul
        v-bind:class="isOpen ? 'block' : 'hidden'"
        class="text-yellow-900 text-sm font-semibold tracking-wide sm:flex sm:justify-between sm:items-center"
      >
        <li class="hover:text-orange-600 w-auto sm:mx-6">
          <router-link to="/">HOME</router-link>
        </li>
        <li class="my-1 hover:text-orange-600 w-auto sm:mx-6">
          <router-link to="/products">PRODUCTS</router-link>
        </li>
        <li class="my-1 hover:text-orange-600 w-auto sm:mx-6">
          <router-link to="/events">EVENTS</router-link>
        </li>
        <li class="my-1 hover:text-orange-600 w-auto sm:mx-6">
          <router-link to="/about">ABOUT US</router-link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
    };
  },
};
</script>