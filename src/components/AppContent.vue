<script>
  export default {
    data() {
      return {
        text: "<--- content here --->"
      }
    }
}
</script>

<template>
  <div class="container">
    <p>{{ text }}</p>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

  .container {
    width: 100%;
    min-height: 200px;
    background-color: $dark;
    @include flex-full (row, center, center);

    p {
      color: white;
      font-size: 5rem;
    }
  }

</style>
