<template>
  <Layout>
    <template slot="page_title">
      Collin O'Connell
    </template>
    <template slot="sub_title">
      Full Stack Developer
    </template>
    <template slot="page_brief">
      Coding, Laravel, Vue, CSS, Accessibility and <a class="text-gold font-bold" href="//www.detcityfc.com">#DCTID</a>
    </template>
    <template slot="main">
      <div class="grey-darkest text-lg font-serif">
        <p>
          Thanks for stopping by if you would like to see some of my work check out my <g-link to="/projects">projects</g-link>.
        </p>
        <p>
          If you would like to talk to me feel free to <g-link to="/contact">contact me.</g-link>
        </p>
      </div>
    </template>
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
