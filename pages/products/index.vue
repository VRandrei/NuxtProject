<template>
  <div>
    <div class="mx-auto max-w-2xl px-4 py-16 sm:px-6 sm:py-24 lg:max-w-7xl lg:px-8">
      <div class="mt-6 grid grid-cols-1 gap-x-6 gap-y-10 sm:grid-cols-2 lg:grid-cols-4 xl:gap-x-8">
        <div v-for="product in products" :key="product.id" class="group relative">
          <NuxtLink :to="`/products/${product.id}`">
          <div class="aspect-h-1 aspect-w-1 w-full p-1 overflow-hidden rounded-md bg-gray-500 lg:aspect-none group-hover:opacity-75 lg:h-80">
            <img :src="product.image" :alt="product.imageAlt" class="h-full w-full rounded-md object-cover object-center lg:h-full lg:w-full" />
          </div>
          <div class="mt-4 flex justify-between">
            <div>
              <h3 class="text-sm text-gray-700">
                <a :href="product.href">
                  <span aria-hidden="true" class="absolute inset-0" />
                  {{ product.title }}
                </a>
              </h3>
            </div>
            <p class="text-sm font-medium text-gray-900">{{ product.price }}$</p>
          </div>
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const { data: { _rawValue: products } } = await useFetch('https://fakestoreapi.com/products');
</script>