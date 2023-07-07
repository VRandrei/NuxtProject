<template>
  <div >
    <div class="pt-6">
      <nav aria-label="Breadcrumb">
        <ol role="list" class="mx-auto flex max-w-2xl items-center space-x-2 px-4 sm:px-6 lg:max-w-7xl lg:px-8">
          <li>
            <div class="flex items-center">
              <a class="mr-2 text-sm font-medium text-gray-900">{{product.category}}</a>
              <svg width="16" height="20" viewBox="0 0 16 20" fill="currentColor" aria-hidden="true" class="h-5 w-4 text-gray-300">
                <path d="M5.697 4.34L8.98 16.532h1.327L7.025 4.341H5.697z" />
              </svg>
              <a class="mr-2 text-sm font-medium text-gray-900">{{product.title}}</a>
            </div>
          </li>
          <li class="text-sm">
            <a :href="product.href" aria-current="page" class="font-medium text-gray-500 hover:text-gray-600">{{ product.name }}</a>
          </li>
        </ol>
      </nav>

      <div class="mx-auto mt-6 max-w-2xl sm:px-6 lg:grid lg:max-w-7xl lg:grid-cols-2 lg:gap-x-8 lg:px-8">
        <div class="aspect-h-5 aspect-w-4 lg:aspect-h-4 lg:aspect-w-3 sm:overflow-hidden">
          <img :src="product.image" :alt="product.image" class="h-full w-full object-cover object-center" style="max-width: 500px; max-height: 800px; border-radius: 10px" />
        </div>
        <div class="details">
          <div class="mt-6 mb-6">
            <h1 class="text-2xl font-bold tracking-tight text-gray-900 sm:text-3xl">{{ product.title }}</h1>
          </div>
          <div class="mt-4 mb-4">
            <p class="text-3xl tracking-tight text-gray-900">${{ product.price }}</p>
          </div>
          <div class="mt-6 mb-6">
            <div class="space-y-6">
              <p class="text-base text-gray-900">{{ product.description }}</p>
            </div>
          </div>
          <div class="mt-10 mb-10">
            <button type="submit" class="flex w-full items-center justify-center rounded-md border border-transparent bg-indigo-600 px-8 py-3 text-base font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">Add to bag</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const {id} = useRoute().params
const { data: { _rawValue: product } } = await useFetch(`https://fakestoreapi.com/products/${id}`, {key: id});
</script>

<style>
.details{
  margin-top: 100px;
}
</style>