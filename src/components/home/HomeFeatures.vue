<template>
</template>

<script>
import VueLogo from '~/assets/images/vue-logo.svg'
import GraphQlLogo from '~/assets/images/graphql-logo.svg'
export default {
  props: ['icon'],
  components: {
    VueLogo,
    GraphQlLogo,
  },
  computed: {
    iconClasses() {
      let classes = []
      return classes
    }
  }
}
</script>
