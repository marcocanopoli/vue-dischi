<template>
  <div>
      <h1>Please wait while the albums are loading...</h1>
      <img src="https://media.giphy.com/media/LwBTamVefKJxmYwDba/giphy.gif" alt="">
  </div>
</template>

<script>
export default {
    name: 'Loader'
}
</script>

<style lang="scss" scoped>
    div {
        text-align: center;

        img {
            height: 200px;
            margin-top: 25px;
        }
    }

</style>