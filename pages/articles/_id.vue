<template>
  <h1>{{ id }}</h1>
</template>


<script>
// こういう書き方
export default {
  asyncData({params}) {
    const {id} = params
    return {
      id
    }
  }
}
</script>
