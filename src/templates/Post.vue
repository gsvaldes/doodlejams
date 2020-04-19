<template>
  <Layout>
    <div class="post">
      <h1 class="post__title">{{$page.post.title}}</h1>
      <p>{{$page.post.date}}</p>
      <div class="post__img">
        <g-image :src="$page.post.image" />
      </div>
      <div>
        <g-link
          :to="tag.path"
          style="padding-right: .25em"
          v-for="tag in edge.node.tags"
          :key="tag.id"
        >#{{tag.id}}</g-link>
      </div>
      <div v-html="$page.post.content"></div>
    </div>
  </Layout>
</template>

<page-query>
query ($path: String!) {
  post: post (path: $path) {
    title
    content
    image
    tags {
      id
      path
    }
}
}
</page-query>

<script>
export default {
  components: {},
  metaInfo() {
    return {
      title: this.$page.post.title
    };
  }
};
</script>

<style>
h2 {
  padding-top: 0.8em;
  padding-bottom: 0.6em;
}

.post__img {
  width: 100%;
  text-align: center;
}

.post__img img {
  width: 100%;
}
</style>