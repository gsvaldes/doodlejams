<template>
  <Layout>

    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <!-- <g-image alt="Example image" src="~/favicon.png" width="135" /> -->

    <post v-for="edge in $page.allPost.edges" :key="edge.node.id">
      <h2><g-link :to="edge.node.path">{{edge.node.title}}</g-link></h2>
      <div class="article-meta">{{edge.node.date }}</div>
      <p>{{edge.node.abstract}}</p>
    </post>

    <p class="home-links">
      <a href="#" rel="noopener">Instagram</a>
    </p>

  </Layout>
</template>

<page-query>
query {
  allPost {
    edges {
      node {
        title
        abstract
        image
        path
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Doodlejams'
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
