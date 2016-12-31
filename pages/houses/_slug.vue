<template>
  <section class="container">
    <h1>{{text.name}}</h1>
    <p>{{text.description}}</p>
  </section>
</template>

<script>
import content from '~/content.json';

export default {
  data ({ params, error }) {
    function findItem(item) {
      console.log(`item.slug:${item.slug}, params.slug:${params.slug}`)
      return item.slug === params.slug
    }
    const text = content.houses.find(findItem)
    if (text) {
      return { text: content.houses.find(findItem)}
    } else {
      error({ message: 'User not found', statusCode: 404 })
    }
  }
}
</script>

<style scoped>

</style>
