<template>
  <Layout>
    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <!-- <g-image alt="Example image" src="~/favicon.png" width="135" /> -->

    <post v-for="edge in $page.allPost.edges" :key="edge.node.id">
      <h2>
        <g-link :to="edge.node.path">{{edge.node.title}}</g-link>
      </h2>
      <div class="article-meta">{{edge.node.date }}</div>
      <p>{{edge.node.abstract}}</p>
      <div>
        <g-link
          :to="tag.path"
          style="padding-right: .25em"
          v-for="tag in edge.node.tags"
          :key="tag.id"
        >#{{tag.id}}</g-link>
      </div>
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
        tags {
          id
          path
        }
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: "Doodlejams"
  }
};
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
