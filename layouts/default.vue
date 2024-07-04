<script setup lang="ts">
const items: Array<{ id: string; name: string; link: string }> = [

  { id: "one", name: 'Home', link: '/' },

  { id: "two", name: 'About', link: "/about" },

];

useHead
({
  title: 'My App',
  meta: [
    { name: 'olivia\'s website', content: 'My amazing site.' }
  ],
  bodyAttrs: {
    class: 'flex flex-col min-h-screen'
  }})
</script>

<template>
  <div class="flex-grow">
  <navbar :items="items">
    <template #navbar-title>
      navigation 
    </template>
    <template v-for="item in items" v-slot:[item.name]>
    <li><a>
      <button class="btn btn-xs sm:btn-sm md:btn-md lg:btn-lg">
        <NuxtLink class="link" :to="item.link">{{ item.name }}</NuxtLink>
      </button>
    </a></li>
    </template>
    <template #theme>
      <div class="p-3">
        <Themetoggle/>
      </div>
    </template>
  </navbar>
  <Apphero>
    <template #title>
      <slot name="title"/>
    </template>
    <template #content>
      <slot name="content"/>
    </template>
    <template #button>
      <slot name="button"/>
    </template>
  </Apphero>
  </div>
    <Appfooter >
      <template #footer-content>
        here is a footer
      </template>
  </Appfooter>
</template>