<template>
  <Layout>
    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <div style="height:800px;margin-left:300px;padding:20px">
      <div
        style="border:1px solid black;width:600px;margin-bottom:20px"
        v-for="post in $page.posts.edges"
        :key="post.id"
      >
        <div
          style="border-bottom:1px solid black;height:40px;line-height:40px;padding-left:10px"
        >
          <g-link :to="'/post/' + post.node.id">
            ☆ {{ post.node.title }}
          </g-link>
          <span>by {{ post.node.author }}</span>
        </div>
        <div style="height:80px;padding-left:10px">
          <p>created at : {{ post.node.created_at }}</p>
          <p>
            <span v-for="tag in post.node.tags" :key="tag.id">
              <g-link :to="'/tag/' + tag.id">
                {{ tag.title }}
              </g-link>
              &nbsp;&nbsp;
            </span>
          </p>
        </div>
      </div>
      <Pager :info="$page.posts.pageInfo" />
    </div>
  </Layout>
</template>

<page-query>
query($page: Int){
  posts:allStrapiPost(perPage: 2, page: $page) @paginate {
    pageInfo {
      totalPages
      currentPage
    }
    edges{
      node{
        id
        title
        author
        created_at
        tags{
          id
          title
        }
      }
    }
  }
}

</page-query>

<script>
import { Pager } from 'gridsome'
export default {
  name: 'HomePage',
  components: {
    Pager,
  },
  metaInfo: {
    title: 'Hello, world!',
  },
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
