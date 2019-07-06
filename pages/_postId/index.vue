<template>
  <div id="post">
    <div id="thumbnail"/>
    <h1 class="title"/>
    <p class="content"/>
  </div>
</template>

<script>
export default {
  asyncData(context) {
    return context.app.$storyapi
      .get('cdn/stories/' + context.params.postId, {
        version: 'draft'
      })
      .then(res => {
        console.log(res.data)
      })
  }
}
</script>
