<template>
  <div>
    <header>
      <nav class="mx-auto flex max-w-7xl items-center justify-between p-6 lg:px-8" aria-label="Global">
        <div class="flex lg:flex-1">
          <div class="-m-1.5 p-1.5">
            <NuxtLink class="text-sm font-semibold leading-6 text-gray-900" to="/">Nuxt 3 SSR</NuxtLink>
          </div>
        </div>
        <div class="flex lg:hidden">
          <button type="button" class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700" @click="mobileMenuOpen = true">
            <span class="sr-only">Open main menu</span>
            <Bars3Icon class="h-6 w-6" aria-hidden="true" />
          </button>
        </div>
        <PopoverGroup class="hidden lg:flex lg:gap-x-12">
          <NuxtLink class="text-sm font-semibold leading-6 text-gray-900" to="/">Home</NuxtLink>
          <NuxtLink class="text-sm font-semibold leading-6 text-gray-900" to="/about">About</NuxtLink>
          <NuxtLink class="text-sm font-semibold leading-6 text-gray-900" to="/products">Products</NuxtLink>
        </PopoverGroup>
        <div class="hidden lg:flex lg:flex-1 lg:justify-end">
          <NuxtLink class="text-sm font-semibold leading-6 text-gray-900" to="/login">Log in<span>&rarr;</span></NuxtLink>
        </div>
      </nav>
     <ClientOnly>
      <Dialog as="div" class="lg:hidden" @close="mobileMenuOpen = false" :open="mobileMenuOpen">
        <div class="fixed inset-0 z-10" />
          <DialogPanel class="fixed inset-y-0 right-0 z-10 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10">
            <div class="flex items-center justify-between">
              <div class="-m-1.5 p-1.5">
                <NuxtLink class="text-sm font-semibold leading-6 text-gray-900" to="/">Nuxt 3 SSR</NuxtLink>
              </div>
              <button type="button" class="-m-2.5 rounded-md p-2.5 text-gray-700" @click="mobileMenuOpen = false">
                <span class="sr-only">Close menu</span>
                <XMarkIcon class="h-6 w-6" aria-hidden="true" />
              </button>
            </div>
            <div class="mt-6 flow-root">
              <div class="-my-6 divide-y divide-gray-500/10">
                <div class="space-y-2 py-6">
                  <NuxtLink class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50" to="/">Home</NuxtLink>
                  <NuxtLink class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50" to="/about">About</NuxtLink>
                  <NuxtLink class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50" to="/products">Products</NuxtLink>
                </div>
                <div class="py-6">
                  <NuxtLink class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50" to="/login">Log in</NuxtLink>
                </div>
              </div>
            </div>
          </DialogPanel>
      </Dialog>
     </ClientOnly>
    </header>

    <div>
      <slot/>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import {Dialog, DialogPanel, PopoverGroup,} from '@headlessui/vue'
import {Bars3Icon, XMarkIcon,} from '@heroicons/vue/24/outline'
const mobileMenuOpen = ref(false)
</script>
