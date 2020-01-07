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
      <v-app-bar-nav-icon class="hidden-md-and-up" @click="drawer=!drawer"/>
    </v-app-bar>
    <v-navigation-drawer
      v-show="drawer"
      v-model="drawer"
      :right="right"
      absolute
      temporary
    >
      <v-list>
        <template v-for="(btn, index) in buttons">
          <v-list-item :key="btn.name" :to="{name: btn.link}">
            <v-list-item-content>
              <v-list-item-title>
                {{btn.name}}
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-divider
            v-if="index + 1 < buttons.length"
            :key="index"
          ></v-divider>
        </template>
      </v-list>
    </v-navigation-drawer>
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
      drawer: false,
      right: true,
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
