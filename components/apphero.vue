<template>
<div class="hero bg-base-200 min-h-screen flex-grow">
  <div class="hero-content text-center">
    <div class="max-w-md">
      <h1 class="text-5xl font-bold">
        <slot name="title">

        </slot>
      </h1>
      <p class="py-6">
        <slot name="content">
          
        </slot>
      </p>
      <button class="btn btn-outline btn-xs sm:btn-sm md:btn-md lg:btn-lg">
        <slot name="button">

        </slot>
      </button>
    </div>
  </div>
</div>
</template>