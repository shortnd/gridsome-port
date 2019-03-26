<template>
  <Layout>
    <template slot="page_title">
      Projects
    </template>
    <template slot="main">
        <div class="mx-auto md:w-4/5 sm:w-full container">
          <h2 class="text-center text-rouge text-2xl uppercase">Current Projects</h2>
          <div class="flex justify-between flex-wrap mb-12">
            <g-link class="flex-1 no-underline shadow p-4 m-2" v-for="{node} in $page.projects.edges" :key="node.id">
              <h3 class="font-thin text-grey-darkest">{{ node.title }}</h3>
              <p class="text-grey-darker md:w-full w-full sm:w-full lg:w-full p0">
                {{ node.description }}
              </p>
            </g-link>
          </div>

          <h2 class="text-center text-rouge text-2xl uppercase mb-3">Private Projects</h2>
          <p>
            If you are intersted in hearing about some of the private projects I have worked on please <g-link to="/contact">contact me</g-link>.
          </p>
        </div>
    </template>
  </Layout>
</template>

<page-query>
query Projects {
  projects: allProject {
    edges {
      node {
        id
        title
        path
        description
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo() {
    return {
      title: "Projects"
    }
  }
}
</script>

<style>
#main p{
  width: 100%;
  padding:0
}
</style>
