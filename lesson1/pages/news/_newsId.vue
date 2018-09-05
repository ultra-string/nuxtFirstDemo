<template>
  <div>
    <h2>News-content：{{$route.params.newsId}}</h2>
    <ul>
      <li>
        <a href="/">返回首页</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  validate({params}) {
    return /^\d+$/.test(params.newsId)
  }
}
</script>

<style>

</style>

