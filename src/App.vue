<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="headline">
        <span>minuro's portfolio</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <LinkButton class="mr-2 hidden-sm-and-down"
      v-for="(btn, index) in buttons" 
      :key="index"
      :link="btn.link"
      :name="btn.name"
      />
      <v-app-bar-nav-icon class="hidden-md-and-up" @click="toggleSideMenu"/>
    </v-app-bar>
    <SideMenu :right="right" :buttons="buttons" />
    <v-content>
      <router-view/>
    </v-content>
  </v-app>
</template>

<script>
import LinkButton from './components/LinkButton'
import SideMenu from './components/SideMenu'
import buttons from './assets/buttons.json'
import { mapActions } from 'vuex'

export default {
  name: 'App',
  data () {
    return {
      right: true,
      buttons: buttons
    }
  },
  components:{
    LinkButton,
    SideMenu
  },
  methods: {
    ...mapActions(['toggleSideMenu'])
  }
}
</script>
