<template>
  <div class="flex flex-col min-h-screen relative font-sans">
    <a href="#" class="absolute pin-t pin-l p-3 bg-rouge text-gold z-50" tabindex="0" @click.prevent="focusMain" id="skip">Skip To Content</a>
    <div id="body" class="flex-1">
      <header class="bg-black text-white sticky z-10">
        <div class="bg-rouge h-1"></div>
        <nav class="container p-2 flex flex-1 md:justify-between md:item-center clearfix mx-auto flex-col md:flex-row">
          <a href="/" class="text-left align-middle text-2xl text-white no-underline sm:block md:inline-block hover:text-gold focus:text-gold sm:mb-3">coconnell.me</a>
          <div class="flex-1 flex mb:text-right md:justify-end md:items-center sm:text-left sm:flex-col md:flex-row">
            <g-link class="block text-white no-underline md:px-2 uppercase hover:text-gold focus:text-gold sm:px-0 py-2 md:border-none sm:border-b sm:border-rouge sm:hover:border-gold sm:focus-border-gold border-b border-rouge" to="/about">About</g-link>
            <g-link class="block text-white no-underline md:px-2 uppercase hover:text-gold focus:text-gold sm:px-0 py-2 md:border-none sm:border-b sm:border-rouge sm:hover:border-gold sm:focus-border-gold border-b border-rouge" to="/projects">Projects</g-link>
            <g-link class="block text-white no-underline md:px-2 uppercase hover:text-gold focus:text-gold sm:px-0 py-2 md:border-none sm:border-b sm:border-rouge sm:hover:border-gold sm:focus-border-gold border-b border-rouge" to="/contact">Contact</g-link>
          </div>
        </nav>
      </header>
      <section id="hero" class="bg-rouge h-100 relative py-32" role="complementary">
        <div class="container mx-auto text-center align-middle">
          <h1 v-if="$slots.page_title" class="text-5xl font-bold text-white uppercase">
            <slot name="page_title"/>
          </h1>
          <h2 v-if="$slots.sub_title" class="text-2xl font-semibold text-grey-lightest uppercase">
            <slot name="sub_title" />
          </h2>
          <p v-if="$slots.page_brief" class="text-white mt-6 text-xl">
            <slot name="page_brief"/>
          </p>
        </div>
      </section><!--/#hero-->
      <main id="main" class="mt-16 md:w-4/5 sm:w-full px-2 text-grey-darkest container mx-auto">
        <slot name="main"/>
      </main>
    </div>
    <footer class="bg-rouge pin-b">
      <div class="container mx-auto py-6">
        <p class="text-gold text-center">
          &copy; Copyright 2019 <a class="text-bold text-gold" href="//coconnell.me">coconnell.me</a> - Site build with <a class="text-bold text-gold" href="//gridsome.org">Gridsome</a>
        </p>
      </div>
    </footer>
  </div>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<script>
export default {
  props: [
    'page_title',
    'sub_title',
    'page_brief',
    'main'
  ],
  methods: {
    focusMain() {
      const main = document.getElementById('main');
      main.tabIndex = '-1';
      main.focus();
      main.removeAttribute('tabindex');
    }
  }
}
</script>


<style>
@tailwind preflight;
@tailwind components;
@tailwind utilities;
#skip {
  left: -100%;
}
#skip:focus{
  left:0
}
#main a {
  @apply text-rouge font-sans font-medium
}
#main p {
  @apply mb-10 mx-auto px-2
}
@media (min-width: 576px) {
  #main p {
    width: 100%;
  }
}
@media (min-width: 768px) {
  #main p {
    width: 50%;
  }
}
</style>
