<template>
  <section class="container">
    <img src="../assets/img/logo.png" alt="Nuxt.js Logo" class="logo" />
    <h1 class="title">
      A minimalistic framework <br>for server-rendered Vue.js applications
    </h1>
    <nuxt-link class="button" to="/about">
      About page
    </nuxt-link>
    <ul class="content">
      <li v-for="item in content">
        <nuxt-link :to="'/houses/'+item.slug">{{ item.name }}</nuxt-link>
      </li>
    </ul>
  </section>
</template>

<script>
import content from '~/content.json';
export default {
  data () {
    return { content: content.houses }
  }
}
</script>

<style scoped>
.title
{
  margin: 50px 0;
}
</style>
