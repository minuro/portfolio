<template>
  <v-navigation-drawer
    v-show="$store.state.drawer"
    v-model="$store.state.drawer"
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
</template>

<script>
export default {
  props: {
    right: Boolean,
    buttons: Array
  }
}
</script>