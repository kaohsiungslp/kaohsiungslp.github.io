<template><div v-html="postData"></div></template>
<script setup>
import { google } from 'googleapis'

const blogger = google.blogger({
  version: 'v3',
  auth: 'AIzaSyBHMTzOKmho_qUMw_pe6niG4YhRYd_86lI'
})
const postData = ref('')
blogger.posts.get(
  { blogId: '4363066856595833159', postId: '8090240234365993769' },
  (err, res) => {
    if (err) {
      throw err
    }
    postData.value = res.data.content
  }
)
</script>
