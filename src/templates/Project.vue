<template>
  <Layout>
    <template slot="page_title">
      {{ $page.project.title }}
    </template>
    <template slot="main">
      <div v-html="$page.project.content"></div>
    </template>
  </Layout>
</template>

<page-query>
query Project($path: String!) {
  project: project(path: $path) {
    title
    content
  }
}
</page-query>

<script>
export default {
  metaInfo() {
    return {
      title: this.$page.project.title,
      // siteDescription: this.$page.project.description
    }
  }
}
</script>

<style>

</style>
