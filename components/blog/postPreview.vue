/* eslint-disable */
<template>
  <section id="posts">
    <nuxt-link
      :to="id">
      <article class="post-preview">
        <div
          :style="{backgroundImage: 'url(' + thumbnailUrl + ')'}"
          class="post-preview-thumbnail"/>
        <div class="post-preview-content">
          <h2 class="title">{{ title }}</h2>
          <p class="Excerpt">{{ excerpt }}</p>
        </div>
      </article>
    </nuxt-link>
  </section>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    excerpt: {
      type: String,
      required: true
    },
    thumbnailUrl: {
      type: String,
      required: true
    },
    id: {
      type: String,
      required: true
    }
  }
}
</script>
<style scoped>
a {
  text-decoration: none;
  color: black;
}
.post-preview {
  display: flex;
  justify-items: center;
  border-radius: 10px;
  box-shadow: 1px, 1px, 5px, 1px rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 20rem;
  margin: 1rem;
}
.post-preview-thumbnail {
  background-position: center;
  background-size: cover;
  width: 90%;
  height: 14rem;
}
.post-preview-content {
  text-align: center;
  padding: 1rem;
}
@media (min-width: 35rem) {
  post-preview {
    width: 25rem;
    margin: 1rem;
  }
}
</style>
