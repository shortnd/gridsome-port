<template>
  <Layout customId="about">
    <template slot="page_title">
      <!-- About Us -->
      {{ $page.about.pageTitle }}
    </template>
    <template slot="sub_title">
      <!-- Learn More About Me -->
      {{ $page.about.subTitle }}
    </template>
    <template slot="main">
      <div class="text-center" v-html="$page.about.content" />
    </template>
  </Layout>
</template>

<page-query>
query {
  about: myPages(path: "/content/pages/about") {
    pageTitle
    subTitle
    content
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'About'
  }
}
</script>


