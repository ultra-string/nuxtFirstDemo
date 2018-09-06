<template>
  <div>
    news page
    <h5>newId：{{$route.params.newsId}}</h5>
    <a href="/"><button>跳转到首页</button></a>
    <ul>
      <li>
        <a href="/news/123">新闻123</a>
      </li>
      <li>
        <a href="/news/a456">新闻456</a>
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  transition: 'test'
}
</script>

<style>

</style>

