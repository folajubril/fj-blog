<template>
  <section class="Blog-home">
    <div class="jumbotron">
      <div class="row">
        <!-- Blog Entries Column -->
        <div class="col-md-8">
          <h1 class="my-4">Insights from FJ
            <br>
            <small>Feed your mind here</small>
          </h1>
          <postPreview
            v-for= "post in posts"
            :key= "post.id"
            :title= "post.title"
            :excerpt= "post.excerpt"
            :thumbnail-url= "post.thumbnail"
            :id= "post.id"/>
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

        <!-- Sidebar Widgets Column -->
        <div class="col-md-4">

          <!-- Search Widget -->
          <div class="card my-4">
            <h5 class="card-header">Search</h5>
            <div class="card-body">
              <div class="input-group">
                <input 
                  type="text" 
                  class="form-control" 
                  placeholder="Search for...">
                <span class="input-group-btn">
                  <button 
                    class="btn btn-secondary" 
                    type="button">Go!</button>
                </span>
              </div>
            </div>
          </div>
          <!-- Categories Widget -->
          <div class="card my-4">
            <h5 class="card-header">Categories</h5>
            <div class="card-body">
              <ul class="list-unstyled mb-0">
                <li>
                  <a href="#">Web Design</a>
                </li>
                <li>
                  <a href="#">HTML</a>
                </li>
                <li>
                  <a href="#">Freebies</a>
                </li>
                <li>
                  <a href="#">JavaScript</a>
                </li>
                <li>
                  <a href="#">CSS</a>
                </li>
                <li>
                  <a href="#">Tutorials</a>
                </li>
              </ul>
            </div>
          </div>

          <!-- Side Widget -->
          <div class="card my-4">
            <h5 class="card-header">Side Widget</h5>
            <div class="card-body">
              You can put anything you want inside of these side widgets. They are easy to use, and feature the new Bootstrap 4 card containers!
            </div>
          </div>

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
  asyncData(context) {
    return context.app.$storyapi
      .get('cdn/stories', {
        version: 'draft',
        starts_with: 'blog/'
      })
      .then(res => {
        return {
          posts: res.data.stories.map(bp => {
            return {
              id: bp.content.slug,
              title: bp.content.title,
              excerpt: bp.content.excerpt,
              thumbnail: bp.content.thumbnail
            }
          })
        }
      })
  }
  // data() {
  //   return {
  //     posts: [
  //       {
  //         title: 'This is the first post',
  //         thumbnail: 'http://www.gettyimages.com/detail/875611350',
  //         excerpt: 'Post about things i like and dont like',
  //         id: 'first-post'
  //       },
  //       {
  //         title: 'This is the second post',
  //         thumbnail: slider,
  //         excerpt:
  //           'Post about things i dream of and things i aspire to be Post about things i dream of and things i aspire to bePost about things i dream of and things i aspire to bePost about things i dream of and things i aspire to be Post about things i dream of and things i aspire to be',
  //         id: 'second-post'
  //       }
  //     ]
  //   }
  // }
}
</script>
<style scoped>
*,
.Blog-home {
  margin-top: 15px;
}
</style>
