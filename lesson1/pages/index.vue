<template>
  <div>
    <ul>
      <li>
        <nuxt-link :to="{name: 'index'}">Home</nuxt-link>
      </li>
      <li>
        <nuxt-link :to="{name: 'about', query: {name: 'jason', age: 18}}">About</nuxt-link>
      </li>
      <li>
        <nuxt-link :to="{name: 'news', params: {newsId: 666}}">News</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>

export default {

}
</script>

<style>

</style>

