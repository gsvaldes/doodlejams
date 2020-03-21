<template>
    <Layout>
        <div class="postPage">
            <h1 class="postPage__title">{{$page.post.title}}</h1>
            <p>{{$page.post.author}}</p>
            <p>{{$page.post.date}}</p>
            <div class="postPage_img">
                <g-image :src="$page.post.image" width="500"/>
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
    author
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
  padding-top: .8em;
  padding-bottom: .6em;
}

</style>