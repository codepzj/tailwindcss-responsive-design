<template>
  <div class="bg-gray-900 text-white px-6 py-3.5 shadow md:flex justify-between items-center">
    <div class="flex items-center">
      <span class="text-green-500 text-lg">
        <i class="bi bi-messenger"></i>
      </span>
      <h1 class="ml-1.5 text-lg" @click="toggleOpen">Designer</h1>
    </div>
    <span class="md:hidden absolute right-6 top-3.5 text-2xl">
      <i :class="[open ? 'bi bi-x' : 'bi bi-filter-right']" @click="toggleOpen"></i>
    </span>
    <ul
      class="text-white bg-gray-900 rounded-bl-xl md:flex md:items-center md:px-3 px-8 md:py-0 py-3 md:w-auto md:mx-0 ml-4 w-full md:static absolute duration-500 ease-in-out"
      :class="[open ? 'left-0' : 'left-[-120%]']">
      <li class="md:px-4 py-1.5" v-for="link in links">
        <a :href="link.link" class="hover:text-green-600 focus:text-green-600">{{ link.name }}</a>
      </li>
      <Button>Get Started</Button>
    </ul>
  </div>
</template>
<script setup>
import { ref } from 'vue';
import Button from './Button.vue';
let open = ref(false)
let links = [
  { name: "Brand", link: "#" },
  { name: "Product", link: "#" },
  { name: "Cart", link: "#" },
  { name: "About", link: "#" }
]

let toggleOpen = () => {
  open.value = !open.value
}
</script>