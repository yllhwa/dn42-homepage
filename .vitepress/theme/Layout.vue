<script setup lang="ts">
import { useData } from 'vitepress'
import Header from './Header.vue'
import Footer from './Footer.vue';

// https://vitepress.dev/reference/runtime-api#usedata
const { site, frontmatter } = useData()
</script>

<template>
  <Header />
  <div class="content">
    <Content />
  </div>
  <Footer />
  <!-- <div v-if="frontmatter.home">
    <ul>
      <li><a href="/markdown-examples.html">Markdown Examples</a></li>
      <li><a href="/api-examples.html">API Examples</a></li>
    </ul>
  </div>
  <div v-else>
    <a href="/">Home</a>
    <Content />
  </div> -->
</template>

<style>
.content {
  padding: 8px 50px;
  padding-bottom: 36px;
}
</style>