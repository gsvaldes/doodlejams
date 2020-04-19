<template>
  <Layout>
    <div class="post">
      <h1 class="post__title">{{$page.post.title}}</h1>
      <p>{{$page.post.date}}</p>
      <div class="post__img">
        <g-image :src="$page.post.image" />
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
