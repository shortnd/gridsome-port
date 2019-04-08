<template>
  <Layout>
    <template slot="page_title">
      <!-- Collin O'Connell -->
      {{ $page.index.pageTitle }}
    </template>
    <template slot="sub_title">
      <!-- Full Stack Developer -->
      {{ $page.index.subTitle }}
    </template>
    <template slot="page_brief">
      <div v-html="$page.index.pageBrief"></div>
    </template>
    <template slot="main">
      <div class="grey-darkest text-lg font-serif"
        v-html="$page.index.content">
      </div>
    </template>
  </Layout>
</template>

<page-query>
query {
  projects: allProject {
    edges {
      node {
        id
        title
        path
      }
    }
  }
  index: myPages(path: "/content/pages") {
    pageTitle
    subTitle
    pageBrief
    content
  }
}
</page-query>

<script>
export default {
  // metaInfo: {
  //   title: 'Hello, world!'
  // }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
