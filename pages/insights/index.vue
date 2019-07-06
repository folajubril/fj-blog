c<template>
  <section class="Blog-home">
    <div class="jumbotron">
      <div class="row">
        <!-- Blog Entries Column -->
        <div class="col-md-8">
          <h1 class="my-4">Insights from FJ
            <br>
            <small>Feed your mind here</small>
          </h1>
          <div class="row">
            <div class="col-md-8">
              <div class="post-card">
                <postPreview
                  v-for= "post in posts"
                  :key= "post.id"
                  :title= "post.title"
                  :excerpt= "post.excerpt"
                  :thumbnail-url= "post.thumbnail"
                  :id= "post.id"/>
              </div>
            </div>
          </div>
          
          <!-- Pagination -->
          <ul class="pagination justify-content-center mb-4">
            <li class="page-item">
              <a 
                class="page-link" 
                href="#">&larr; Older</a>
            </li>
            <li 
              class="page-item disabled">
              <a 
                class="page-link"
                href="#">Newer &rarr;</a>
            </li>
          </ul>

        </div>
      </div>
      <!-- /.row -->
    </div>
    <!-- /.container -->
  </section>
</template>
<script>
import postPreview from '@/components/blog/postPreview'
import slider from '~/static/slider.jpg'
export default {
  components: {
    postPreview,
    slider
  },
  data() {
    return {
      posts: [
        {
          title: 'This is the first post',
          thumbnail: 'http://www.gettyimages.com/detail/875611350',
          excerpt: 'Post about things i like and dont like',
          id: 'first-post'
        },
        {
          title: 'This is the second post',
          thumbnail: slider,
          excerpt:
            'Post about things i dream of and things i aspire to be Post about things i dream of and things i aspire to bePost about things i dream of and things i aspire to bePost about things i dream of and things i aspire to be Post about things i dream of and things i aspire to be',
          id: 'second-post'
        }
      ]
    }
  }
  // .catch(error => {
  //   error({ statusCode: 404, message: 'Post not found' })
  // })
}
//  asyncData(context) {
//     return context.app.$storyapi
//       .get('cdn/stories', {
//         version: 'draft',
//         starts_with: 'blog/'
//       })
//       .then(res => {
//         console.log(res)
//         return {
//           posts: res.data.stories.map(bp => {
//             return {
//               id: bp.slug,
//               title: bp.content.title,
//               excerpt: bp.content.Summary,
//               thumbnail: bp.content.thumbnailUrl
//             }
//           })
//         }
//       })
//  }
</script>
<style scoped>
*,
.Blog-home {
  margin-top: 15px;
}
.post-card {
  height: 100px;
  align-content: flex;
  margin-left: 15px;
  width: 100%;
}
</style>
