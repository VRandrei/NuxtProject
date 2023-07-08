<template>
    <div >
      <div class="mx-auto max-w-7xl py-24 sm:px-6 sm:py-32 lg:px-8 container">
          <div class="mx-auto max-w-md text-center lg:mx-0 lg:flex-auto lg:py-20 lg:text-left">
            <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Try the power of Nuxt 3</h2>
            <p class="mt-6 text-lg leading-8 text-gray-900">A demo web application that will inspire you to create your own project!</p>
            <div class="mt-10 flex items-center justify-center gap-x-6 lg:justify-start">
              <a href="#" class="rounded-md bg-gray-900 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-gray-700 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-white"><NuxtLink to="/products">Get started</NuxtLink></a>
              <a href="#" class="text-sm font-semibold leading-6 text-gray-900"><NuxtLink to="/about">Learn more<span aria-hidden="true">→</span></NuxtLink> </a>
            </div>
          </div>
        <Loader/>
      </div>
    </div>
</template>

<style>
.container{
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-right: 200px;
}
</style>
