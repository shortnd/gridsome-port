<template>
  <Layout>
    <template slot="page_title">
      About Us
    </template>
    <template slot="sub_title">
      Learn More About Me
    </template>
    <!-- <h1>About us</h1> -->
    <template slot="main">
      <div class="text-center">
        <a class="block" href="https://github.com/shortnd">Github</a>
        <a class="block" href="https://twitter.com/shortnd">Twitter</a>
        <a class="block" href="#">Linkin</a>
      </div>
    </template>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'About us'
  }
}
</script>
