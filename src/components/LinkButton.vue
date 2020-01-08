<template> 
  <router-link :to="{ name: link }">
    <v-btn color="info" min-width="80px">
      {{name}}
    </v-btn>
  </router-link>
</template> 

<script>
export default {
  props: {
    link: String,
    name: String
  }
}
</script>

<style lang="scss">
a {
    text-decoration: none;
}
</style>
