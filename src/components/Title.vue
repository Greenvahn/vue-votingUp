
<template>
  <div class="container">
    <h2 class="title has-text-centered dividing-header is-3">{{msg}}</h2>
  </div>
</template>

<script>
export default {
  name: 'title',
  props: {
    msg: String
  }
}
</script>

<style lang="scss">
.title{
  margin-top: 35px;
}
</style>

 