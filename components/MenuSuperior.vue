<template>
  <header
    x-data="{ mobileMenuOpen : false }"
    class="flex flex-wrap flex-row justify-between md:items-center md:space-x-4 bg-white py-6 px-6 relative font-extralight"
  >
    <a href="/" class="block">
      <span class="ext-indigo-600 hover:text-gray-400 font-light text-2xl "
        >sergio perea</span
      >
    </a>
    <button
      @click="mobileMenuOpen = !mobileMenuOpen"
      class="inline-block md:hidden w-8 h-8 bg-gray-200 text-gray-600 p-1"
    >
      <svg
        fill="currentColor"
        viewBox="0 0 20 20"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          fill-rule="evenodd"
          d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z"
          clip-rule="evenodd"
        ></path>
      </svg>
    </button>
    <nav
      class="absolute md:relative top-16 left-0 md:top-0 z-20 md:flex flex-col md:flex-row md:space-x-6 font-semibold w-full md:w-auto bg-white shadow-md rounded-lg md:rounded-none md:shadow-none md:bg-transparent p-6 pt-0 md:p-0"
      :class="{ flex: mobileMenuOpen, hidden: !mobileMenuOpen }"
      @click.away="mobileMenuOpen = false"
    >
      <a
        href="/"
        class="block py-1 text-gray-600 hover:text-gray-400 font-extralight"
        >Inicio</a
      >
      <a
        href="/about-me"
        class="block py-1 text-gray-600 hover:text-gray-400 font-extralight"
        >About me</a
      >
      <a
        href="/gallery"
        class="block py-1 text-gray-600 hover:text-gray-400 font-extralight"
        >Portfolio</a
      >
      <a
        href="/contact"
        class="block py-1 text-gray-600 hover:text-gray-400 font-extralight"
        >Contact</a
      >
    </nav>
  </header>
</template>
<script>
export default {
  props: {
    posts: {
      type: Array
    }
  },
  data() {
    return {
      mobileMenuOpen: false
    };
  }
};
</script>

<style scoped></style>
