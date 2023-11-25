<script>
  export default {
    props: {
        image: String,
        title: String
    },
    data() {
      return {
      }
    }
  }
</script>

<template>
    <img class="box" :src="image" :alt="title">
    <h4>{{ title }}</h4>
</template>

<style lang="scss" scoped>
    .box {
        width: 170px;
        aspect-ratio: 1 / 1;
    }
    h4 {
        font-size: .8rem;
        width: 170px;
        margin-top: 5px;
        color: white;
    }
</style>
