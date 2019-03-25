<template>
  <Layout>
    <div class="container mx-auto">
      <h2>Projects</h2>
      <ul>
        <li v-for="project in $page.projects.edges" :key="project.node.id">
          <g-link :to="project.node.path">{{ project.node.title }}</g-link>
        </li>
      </ul>
    </div>
  </Layout>
</template>

<page-query>
query Projects{
  projects: allProject {
    edges {
      node {
        id
        title
        path
      }
    }
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
