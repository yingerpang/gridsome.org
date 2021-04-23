<template>
</template>

<script>
import Connect from '~/components/Connect.vue'

export default {
  components: {
    Connect
  }
}
</script>

<style lang="scss">
.home-connect {
  @media screen and (min-width: 850px) {
    & {
      padding: 1%;
    }
  }
 .grid-cols {
    > div:first-child {
      padding: 0 5%;
    }
  }
}

</style>
