<template>
  <div class="flex flex-col min-h-screen relative">
    <a href="#" class="absolute pin-t pin-l p-3 bg-rouge text-gold z-50" tabindex="0" @click.prevent="focusMain" id="skip">Skip To Content</a>
    <div id="body" class="flex-1">
      <header class="bg-black text-white sticky z-10">
        <div class="bg-rouge h-1"></div>
        <nav class="container py-2 flex flex-1 justify-between item-center clearfix mx-auto">
          <a href="/" class="text-left align-middle text-2xl text-white no-underline sm:block md:inline-block hover:text-gold focus:text-gold">coconnell.me</a>
          <div class="flex-1 flex text-right justify-end items-center">
            <!-- NEED TO ADD ROUTES -->
          </div>
        </nav>
      </header>
      <section id="hero" class="bg-rouge h-100 relative py-32" role="complementary">
        <div class="container mx-auto text-center align-middle">
          <h1 class="text-5xl font-bold text-white uppercase">Collin O'Connell</h1>
          <h2 class="text-2xl font-semibold text-grey-lightest uppercase">Full Stack Developer</h2>
          <p class="text-white mt-6 text-xl">
            Coding, Laravel, Vue, CSS, Accessibility and <a class="text-gold font-bold" href="//www.detcityfc.com">#DCTID</a>
          </p>
        </div>
      </section><!--/#hero-->
      <main id="main" class="font-serif text-grey-darkest container mx-auto">
        <slot/>
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
</style>
