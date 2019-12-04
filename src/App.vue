<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline">
        <span>minuro's portfolio</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <router-link :to="{ name: 'home' }">
        Home
      </router-link>
      <router-link :to="{ name: 'about' }">
        About
      </router-link>
      <router-link :to="{ name: 'work' }">
        Work
      </router-link>
      <router-link :to="{ name: 'link' }">
        Link
      </router-link>
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      //
    }
  }
}
</script>
