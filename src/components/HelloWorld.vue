<template>
  <div>
  <div
          v-for="thread in threads"
          class="col-large push-top">
    <h1>{{ thread.title }}</h1>

    <p>
      By <a href="#" class="link-unstyled">Robin</a>, 2 hours ago.
      <span style="float:right; margin-top: 2px;" class="hide-mobile text-faded text-small">3 replies by 3 contributors</span>
    </p>

    <div class="post-list">

      <div v-for="postId in thread.posts" class="post">

        <div class="user-info">
          <a href="#" class="user-name">{{ users[posts[postId].userId].name }}</a>

          <a href="#">
            <img class="avatar-large" :src="users[posts[postId].userId].avatar" alt="">
          </a>

          <p class="desktop-only text-small">107 posts</p>
        </div>

        <div class="post-content">
          <div>
            {{ posts[postId].text }}
          </div>
        </div>

        <div class="post-date text-faded">
          {{ posts[postId].publishedAt }}
        </div>
      </div>

    </div>
  </div>
  </div>
</template>

<script>
import sourceData from '@/data'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      threads: sourceData.threads,
      posts: sourceData.posts,
      users: sourceData.users
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
