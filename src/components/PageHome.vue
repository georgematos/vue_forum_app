<template>
  <div>
    <div v-for="thread in threads" :key="thread.id" class="col-large push-top">
      <h1>{{ thread.title }}</h1>

      <div class="post-list">
        <div class="post" v-for="postId in thread.posts" :key="postId">
          <div class="user-info">
            <a href="#" class="user-name">{{ userByid(postById(postId).userId).name }}</a>

            <a href="#">
              <img
                class="avatar-large"
                :src="userByid(postById(postId).userId).avatar"
                alt=""
              />
            </a>

            <p class="desktop-only text-small">107 posts</p>

          </div>

          <div class="post-content">
            <div>
              <p>
                {{ postById(postId).text }}
              </p>
            </div>
          </div>

          <div class="post-date text-faded">{{ postById(postId).publishedAt }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import sourceData from '@/data.json'

export default {
  name: 'PageHome',
  props: {
    msg: String
  },
  data () {
    return {
      threads: sourceData.threads,
      posts: sourceData.posts,
      users: sourceData.users
    }
  },
  methods: {
    postById (postId) {
      return this.posts.find((p) => p.id === postId)
    },
    userByid (userId) {
      return this.users.find((u) => u.id === userId)
    }
  }
}
</script>

<style scoped>
</style>
