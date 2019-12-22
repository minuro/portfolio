<template>
  <v-app>
    <v-toolbar app min-height="70px" max-height="70px">
      <v-toolbar-title class="headline">
        <span>minuro's portfolio</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
        <LinkButton class="mr-2"
        v-for="(btn, index) in buttons" 
        :key="index"
        :link="btn.link"
        :name="btn.name"
        />
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
  </v-app>
</template>

<script>
import LinkButton from './components/LinkButton'

export default {
  name: 'App',
  data () {
    return {
      buttons: [
        {
          link: 'home',
          name: 'Home'
        },
        {
          link: 'about',
          name: 'About'
        },
        {
          link: 'work',
          name: 'Work'
        },
        {
          link: 'link',
          name: 'Link'
        }
      ]
    }
  },
  components:{
    LinkButton
  }
}
</script>
