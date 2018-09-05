<template>
  <div>
    about page
    <h5>name: {{$route.query.name}}</h5>
    <h5>age: {{$route.query.age}}</h5>
    <a href="/news"><button>跳转到news</button></a>
  </div>
</template>

<script>

export default {
}
</script>

<style>

</style>

